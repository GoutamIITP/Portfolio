<script>
  import Accordian from './lib/Accordian.svelte';
  import TypedText from './lib/TypedText.svelte';
  import ExperienceBullet from './lib/ExperienceBullet.svelte';
  import ProjectBullet from './lib/ProjectBullet.svelte';
  import Spinner from './lib/Spinner.svelte';
  const timeSpacing = 0.3;
  const maxState = 6;
  let state = 0;

  function nextState () {
    state = state + 1
    if (state == 1) {
      window.setTimeout(nextState, 1000)
    }
    else if (state < maxState) {
      window.setTimeout(nextState, timeSpacing * 1000)
    }
  }

  window.setTimeout(nextState, 2.1 * 1000)

  document.body.addEventListener('click', () => { state = maxState }, true)
</script>

<main>
  <h1>
    <TypedText text="Goutam Kumar Sah" speed={1.5} delay={0.5}/>
  </h1>
  {#if state > 1}
    <p class="mono" style="margin-bottom: 3rem;">
      Developer
    </p>
  {/if}

  {#if state > 2}
    <Accordian>
      <span slot="title">
        About
      </span>
      <span slot="content">
        <p>
        Student at IIT Patna with hands-on experience in web development, data engineering, and data analytics. 
        Passionate about building scalable applications, working with cloud technologies, and solving real-world problems through code and data.
        </p>
        <p>
        I enjoy learning new technologies, collaborating on team projects, and contributing to meaningful work that makes an impact.
        </p>
      </span>
    </Accordian>
  {/if}
  {#if state > 3}
    <Accordian>
      <span slot="title">
        Experience
      </span>
      <span slot="content">
        <ul>
          <ExperienceBullet
            title="Web Development Intern"
            info={[
              'Groveus Informatics Pvt. Ltd.',
              'June 2025 – September 2025 | On-site'
            ]}
            description={
              `Worked with CodeIgniter (PHP framework) to build and maintain dynamic web applications.
              Developed responsive frontend interfaces using HTML, CSS, and Bootstrap.
              Improved website SEO and site structure, resulting in better search ranking.
              Collaborated with team members on real-world client projects, ensuring timely delivery and quality.
              Followed best practices for secure and scalable web development.`
            }
          />
          <ExperienceBullet
            title="Data Engineering Intern"
            info={[
              'Celebal Technologies',
              'June 2025 – August 2025 | Remote'
            ]}
            description={
              `Completed a 2-month internship focused on Azure Data Engineering, ETL workflows, and cloud-based data pipelines.
              Worked with Azure Storage, SQL Databases, PySpark, and Python for data ingestion, processing, and transformation.
              Built and tested ADF pipelines and data lake architectures as part of the Data Engineering Foundation track.
              Gained hands-on exposure to enterprise-level data engineering tools and cloud workflows.
              <a href="https://drive.google.com/file/d/1IdJtrRfWkSODKGSyqey_HsRwqux7rwr1/view?usp=sharing" target="_blank" rel="noopener">View Certificate</a>`
            }
          />
          <ExperienceBullet
            title="Data Analytics Intern"
            info={[
              'GUVI (HCL Group)',
              'June 2025 – September 2025 | Remote'
            ]}
            description={
              `Completed a structured Data Analytics internship conducted by GUVI (HCL Group) in collaboration with IIT Patna.
              Applied Python and SQL for data cleaning, exploratory analysis, and insight generation.
              Worked on real-world datasets to derive actionable insights and improve data-driven decision-making.
              Strengthened fundamentals of analytics, statistics, and problem-solving through hands-on assignments.
              <a href="https://drive.google.com/file/d/16EwLDHq621IJxKeULx2fzVjqfdQEZ0s4/view?usp=sharing" target="_blank" rel="noopener">View Certificate</a>`
            }
          />
          <ExperienceBullet
            title="Sub Coordinator"
            info={[
              'Student Technical Council, IIT Patna',
              '2024 – 2025'
            ]}
            description={
              `Organized and coordinated hybrid technical events, webinars, and coding competitions.
              Collaborated with team members to manage logistics, speaker coordination, and participant engagement.
              Strengthened communication, teamwork, and leadership skills through event planning and execution.
              Acted as a bridge between students and the technical council to ensure smooth event operations.`
            }
          />
        </ul>
      </span>
    </Accordian>
  {/if}
  {#if state > 4}
    <Accordian>
      <span slot="title">
        Projects
      </span>
      <span slot="content">
        <ul>
          <ProjectBullet
            title="Tejasara – E-commerce Website & Admin Panel"
            link="https://www.tejasara.in/"
            description={
              `Full-stack e-commerce platform with cart, checkout, and authentication. Firebase Authentication with role-based admin access. Admin panel for managing orders, users, inventory, and feedback. Firestore CRUD operations, protected routes, real-time updates. Email notifications using EmailJS. Built in collaboration with a real client. <a href="https://tejasara-admin.vercel.app/admin" target="_blank" rel="noopener">View Admin Panel</a>`
            }
          />
          <ProjectBullet
            title="Capstone Project – E-commerce Security Prediction"
            link="https://e-commerce-security-prediction-wokf.onrender.com/"
            description={
              `ML-based web app to detect weak passwords, spam emails, and credit card fraud. Built and trained ML models using Python. Integrated models using Flask for real-time predictions. Deployed on Render.`
            }
          />
          <ProjectBullet
            title="Vendor Performance Analysis"
            link="https://github.com/GoutamIITP/Vendor-Performance-Data-Analytics-End-To-End-Project"
            description={
              `Analyzed vendor and brand performance to identify profitability, pricing, and inventory inefficiencies. Loaded multiple raw CSV files into an SQLite database using Python for structured storage and querying. Cleaned, merged, and transformed data using SQL and Pandas for accurate analysis. Performed EDA to uncover trends, pricing gaps, and slow-moving inventory. Prepared clean datasets for visualization in Power BI to support business decisions.`
            }
          />
        </ul>
      </span>
    </Accordian>
  {/if}
  {#if state > 5}
    <Accordian>
      <span slot="title">
        Skills
      </span>
      <span slot="content">
        <h3>Languages & Frameworks</h3>
        <p>Python, SQL, HTML, CSS, JavaScript, Flask, Bootstrap</p>
        
        <h3>Developer Tools</h3>
        <p>Git, GitHub, VS Code, MySQL Workbench, Google Colab, Firebase, Microsoft Azure (basic)</p>
        
        <h3>Concepts</h3>
        <p>DBMS, OOPS, Machine Learning</p>
        
        <h3>Soft Skills</h3>
        <p>Communication, Analytical Thinking, Teamwork, Collaboration, Work Ethics</p>
      </span>
    </Accordian>
  {/if}
  {#if state > 5}
    <Accordian>
      <span slot="title">
        Contact
      </span>
      <span slot="content">
        <ul>
          <li>Email: <a href="mailto:goutamsah126@gmail.com">goutamsah126@gmail.com</a></li>
          <li>Institute Email: <a href="mailto:goutam_2312res271@iitp.ac.in">goutam_2312res271@iitp.ac.in</a></li>
          <li>Phone: <a href="tel:+917478681535">+91 7478681535</a></li>
          <li>LinkedIn: <a href="https://www.linkedin.com/in/goutam-kumar-sah-562873278/" target="_blank" rel="noopener">View Profile</a></li>
          <li>GitHub: <a href="https://github.com/GoutamIITP" target="_blank" rel="noopener">@GoutamIITP</a></li>
          <li>Portfolio: <a href="https://zippy-sable-9deaa7.netlify.app/" target="_blank" rel="noopener">View Portfolio</a></li>
        </ul>
      </span>
    </Accordian>
  {/if}
  {#if maxState > state && state > 0 }
    <Spinner />
  {/if}
</main>
