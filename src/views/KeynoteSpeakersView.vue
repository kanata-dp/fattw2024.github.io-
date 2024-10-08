<template>
  <div class="keynote-speakers">
    <!-- 主标题 -->
    <h1 class="title1 font-merri">Keynote Speakers</h1>
    
    <!-- 遍历speakers数组，为每个演讲者创建一个部分 -->
    <div v-for="(speaker, index) in speakers" :key="index" class="speaker-section">
      <div class="speaker-content">
        <!-- 演讲者照片 -->
        <div class="speaker-photo">
          <img :src="getImageUrl(speaker.photo)" :alt="speaker.name">
        </div>
        <!-- 演讲者信息 -->
        <div class="speaker-info">
          <h2 class="speaker-name">{{ speaker.name }}</h2>
          <p><span class="bold">Title:</span> {{ speaker.title }}</p>
          <p><span class="bold">Keynotes:</span> {{ speaker.keynote }}</p>
          <p><span class="bold">Abstract:</span> <span class="italic">{{ speaker.abstract }}</span></p>
        </div>
      </div>
      <!-- 演讲者简历 -->
      <div class="speaker-bio">
        <p><span class="bold">Bio:</span> {{ speaker.bio }}</p>
      </div>
      <!-- 如果不是最后一个演讲者，添加分隔线 -->
      <el-divider v-if="index < speakers.length - 1" />
    </div>
    <h1 class="title1 font-merri">Topic Speakers</h1>
  </div>
</template>

<script>
export default {
  data() {
    return {
      // 演讲者数据数组
      speakers: [
        {
          name: "TBD",
          photo: 'tbd.png',
          title: "TBD",
          keynote: "TBD",
          abstract: "TBD",
          bio: "TBD"
        },
        // ... 其他演讲者数据 ...
      ]
    };
  },
  methods: {
    // 获取图片URL的方法
    getImageUrl(name) {
      return new URL(`../assets/image/photos/${name}`, import.meta.url).href
    }
  }
};
</script>

<style lang="less" scoped>
.keynote-speakers {
  color: #333;
  font-family: Arial, sans-serif;
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px;

  // 主标题样式
  .title1 {
    color: #1a365d;
    font-size: 2.5rem;
    margin-bottom: 2rem;
    text-align: center;
  }

  // 每个演讲者部分的样式
  .speaker-section {
    margin-bottom: 2rem;
  }

  // 演讲者内容布局
  .speaker-content {
    display: flex;
    gap: 2rem;
    margin-bottom: 1rem;
  }

  // 演讲者照片样式
  .speaker-photo {
    flex: 0 0 200px;
    img {
      width: 100%;
      height: auto;
      object-fit: cover;
      border-radius: 5px;
    }
  }

  // 演讲者信息样式
  .speaker-info {
    flex: 1;
    p {
      margin-bottom: 0.5rem;
      line-height: 1.6;
    }
  }

  // 演讲者姓名样式
  .speaker-name {
    color: #2a4365;
    font-size: 1.8rem;
    margin-bottom: 1rem;
    font-weight: bold;
    text-decoration: underline;
  }

  // 演讲者简历样式
  .speaker-bio {
    margin-top: 1rem;
    line-height: 1.4;
  }

  // 粗体文本样式
  .bold {
    font-weight: bold;
    color: #2c5282;
  }

  // 斜体文本样式
  .italic {
    font-style: italic;
  }

  // 分隔线样式
  .el-divider {
    margin: 2rem 0;
  }
}

// 响应式布局：在小屏幕上调整布局
@media (max-width: 768px) {
  .keynote-speakers {
    .speaker-content {
      flex-direction: column;
    }

    .speaker-photo {
      margin-bottom: 1rem;
    }
  }
}
</style>


<!--
<template>
  <div class="keynote-speakers">
    <div class="title1 font-merri">Keynote Speakers</div>
    <div class="title2 section-title">Joseph Sifakis, Verimag</div>

    <div class="content">
      <div class="pa">
        <p>
          <span class="bold">Keynote: </span>
          <span>&nbsp;Trustworthy Intelligent Systems – A Daunting Challenge</span>
        </p>
      </div>
      
      <div class="pa">
        <p>
          <span class="bold">Abstract: </span>
          <span class="italic">&nbsp;Systems engineering today is torn between two contradictory trends. On the one hand, the construction of intelligent systems, capable of situation awareness and adaptive decision-making through the use of AI-based components; on the other, the need for trustworthiness guarantees despite the non-explicability of AI components. The situation is exacerbated by the need for increasingly complex and integrated heterogeneous systems, and by the fact that in the current debate on "safe AI", key players in the field are promoting approaches that break with the technical safety concept of systems engineering.</span>
        </p>
        <p class="italic indent">We consider that a system is explainable if it is possible to characterize its relevant behavior by faithful models that lend themselves to analysis and provide a basis for understanding. We argue that AI will remain largely inexplicable. Ignoring this limitation by ascribing anthropomorphic properties to AI systems is technically untenable.</p>
        <p class="italic indent">We need rigorous system design methodologies that integrate model-based and data-driven AI te chniques, enabling in particular the construction of reliable systems integrating unreliable AI components. These methodologies will be characterized by the following important changes: </p>
        <ul>
          <li class="italic indent">Breaking with the idea that system can be guaranteed trustworthy at design time. Instead, systems must be designed to evolve, with no endpoint in their evolution, using computational intelligence, monitoring techniques and over-the-air upgrades.</li>
          <li class="italic indent">A shift from verification to empirical validation using test and simulation, which in principle does not allow confidence levels achieved using model-based methods. </li>
          <li class="italic indent">A better integration of design for dependability into the system development cycle, by jointly addressing safety and security issues, and relying heavily on automated tools.</li>
        </ul>
        <p class="italic indent">We advocate the need for a new foundation for system design that responds to these needs, leveraging knowledge management to compensate for weaknesses arising from the obsolescence of model-based techniques.</p>
      </div>
      
      <div>
        <p>
          <span class="bold">Bio: </span>
          <span>&nbsp;Professor Joseph Sifakis is Emeritus Research Director at Verimag. He has been a full professor at Ecole Polytechnique Fédérale de Lausanne (EPFL) for the period 2011-2016. He is the founder of the Verimag laboratory in Grenoble, a leading laboratory in the area of safety critical systems that he directed for 13 years.</span>
        </p>
        <p class="indent">Joseph Sifakis has made significant and internationally recognized contributions to the design of trustworthy systems in many application areas, including avionics and space systems, telecommunications, and production systems. His current research focuses on autonomous systems, in particular self-driving cars and autonomous telecommunication systems. In 2007, he received the Turing Award, recognized as the "highest distinction in computer science", for his contribution to the theory and application of model checking, the most widely used system verification technique. </p>
        <p class="indent">Joseph Sifakis is a member of six academies and a frequent speaker at international scientific, technical and public forums.</p>
      </div>
    </div>

    <el-divider />

    <div class="title2 section-title">Zheng Zheng, Beihang University</div>

    <div class="content">
      <div class="pa">
        <p>
          <span class="bold">Keynote: </span>
          <span>&nbsp;Reliability and Testing of Reinforcement Learning Systems</span>
        </p>
      </div>

      <div class="pa">
        <p>
          <span class="bold">Abstract: </span>
          <span class="italic">&nbsp;As reinforcement learning (RL) systems proliferate across various domains, ensuring their reliability becomes crucial. This presentation provides a comprehensive examination of RL system reliability and testing, focusing on their unique characteristics. The topics include:</span>
        </p>

        <ul>
          <li class="italic indent">Analysis of reliability and testing attributes of RL systems.</li>
          <li class="italic indent">Construction of metamorphic relations tailored for RL.</li>
          <li class="italic indent">Introduction of coverage metrics specific to RL scenarios.</li>
          <li class="italic indent">Methods for generating test cases for RL environments.</li>
        </ul>

        <p class="italic indent">The talk offers insights into the challenges and methodologies for validating and ensuring the robustness of reinforcement learning systems in diverse applications.</p>
      </div>

      <div>
        <p>
          <span class="bold">Bio: </span>
          <span>&nbsp;Zheng Zheng is a professor at Beihang University and the deputy dean of School of Automation Science and Electrical Engineering. His research work is primarily concerned with software reliability and testing. Recently, He paid more attention on the intelligent software reliability engineering. He is co-author of over 100 journal and conference publications, including IEEE TDSC, IEEE TIFS, IEEE TSE, IEEE TR, IEEE TSC, JSS and so on. He serves for IEEE PRDC2019, IEEE DASC 2019, IEEE ISSRE 2020, IEEE QRS 2021 as PC Co-Chairs, as well as WoSAR 2019, DeIS 2020 and DeIS 2021 as General Co-Chairs. He is Editor-in-chief of Atlantis Highlights in Engineering (Springer Nature), Associate Editor of IEEE TR (2021- ), Elsevier KBS (2018- ) and Springer IJCIS (2012- ) and Guest Editor of IEEE TDSC (2021). He is IEEE Senior Member and IEEE CIS Emerging Technologies TC member.</span>
        </p>
      </div>
    </div>

    <el-divider />

    <div class="title2 section-title">Domenico Cotrone, University of Naples Federico II</div>

    <div class="content">
      <div class="pa">
        <p>
          <span class="bold">Keynote: </span>
          <span>&nbsp;Unveiling the Veil: Towards the Trustworthiness of AI Code Generators</span>
        </p>
      </div>

      <div class="pa">
        <p>
          <span class="bold">Abstract: </span>
          <span class="italic">&nbsp;Nowadays, AI code generators have emerged as powerful tools transforming the software development landscape. These tools promise accelerated productivity and efficiency, but they also raise crucial questions regarding the trustworthiness of the code they produce. This keynote talk delves into the heart of this critical issue, aiming to provide a comprehensive understanding of the topics related to the trustworthiness of AI code generators, focusing on the security and robustness aspects of these AI-powered solutions.</span>
        </p>

        <p class="italic indent">Beginning with an in-depth examination of the security and robustness landscape surrounding AI code generators, the talk will dissect the common threats and risks associated with new technology impacting our everyday lives. From adversarial inputs to poisoning attacks, understanding these potential pitfalls is crucial for developers and organizations alike.</p>
      </div>

      <div>
        <p>
          <span class="bold">Bio: </span>
          <span>&nbsp;Domenico Cotroneo is a Full Professor at the Department of Electrical Engineering and Information Technology, University of Naples Federico II. He is also an IEEE Senior Member. He has served on the Technical Program Committee of important conferences on Dependability and Software Reliability, eg., IEEE/IFIP DSN, IEEE SRDS, Safecomp, IEEE ISSRE, and IEEE ICDS. Domenico’s research activities cover the following areas: dependability assessment of complex software systems, software fault injection, and software performance degradation analysis.</span>
        </p>
      </div>
    </div>

    <el-divider />
    
    <div class="title2 section-title">Ryan Cotterell, ETH Zürich</div> 
    <p class="pa-content p">TBD</p>
  </div>
</template>

<style lang="less" scoped>
.keynote-speakers {
  .section-title {
    margin: 1.6rem 0 0.5rem;
  }

  .content {
    font-size: 2rem;

    .pa {
      margin-bottom: 1rem;
    }

    .bold {
      font-weight: bold;
    }
    .italic {
      font-style: italic;
    }
    .indent {
      text-indent: 2rem;
    }
  }

  .pa-content {
    text-indent: 2rem;
    line-height: 1.6;
  }
}
</style>
-->