<template>
    <div class="bg-[#f5fbfa] py-5">
      <section class="max-w-screen-xl mx-auto p-4" id="about">
        <div class="py-5">
          <div class="flex flex-wrap items-center justify-between px-4 py-2">
            <h1 id="batdombong" class="text-[25px] text-[#000000] font-bold">
              <span class="relative inline-block">
                Experiences
                <span class="absolute left-1/2 bottom-0 w-14 h-[3px] bg-[#15b8a6] -translate-x-1/2"></span>
              </span>
            </h1>
  
            <button
              class="text-[#15b8a6] rounded-[4px] hover:before:bg-border-red-500 relative h-[50px] w-40 overflow-hidden bg-transparent border border-[#15b8a6] px-3 transition-all before:absolute before:bottom-0 before:left-0 before:top-0 before:z-0 before:h-full before:w-0 before:bg-[#15b8a6] before:transition-all before:duration-500 hover:text-white hover:before:left-0 hover:before:w-full">
              <span class="relative z-0">Hire Me</span>
            </button>
          </div>
  
          <div data-aos="zoom-in-down" data-aos-duration="2000"  class="relative border-l-2 border-gray-300 mt-5 pl-6">
            <!-- Sections Loop -->
            <div v-for="(section, index) in sections" :key="index" data-aos="zoom-in-down" data-aos-duration="2000" class="mb-10 relative">
              <div class="absolute -left-[41px] top-2 flex items-center justify-center w-8 h-8 bg-[#002d5b] text-white font-bold rounded-full">
                {{ index + 1 }}
              </div>
              <h3 class="text-[25px] text-start font-bold">{{ section.title }}</h3>
              <div class="grid md:grid-cols-3 gap-4 mt-4">
                <div v-for="(item, idx) in section.items" :key="idx" class="bg-white p-4 shadow-[0px_0px_15px_2px_#e2e8f0] text-start rounded-md">
                  <h4 class="font-bold text-[#002d5b] text-[18px]">{{ item.name }}</h4>
                  <p v-if="item.institution" class="text-gray-600 text-[15px]">{{ item.institution }}</p>
                  <p v-if="item.description" class="text-gray-500 text-[13px] font-normal mt-2">{{ item.description }}</p>
                  <ol v-if="item.details" class="list-decimal p-2">
                    <li v-for="(detail, i) in item.details" :key="i" class="text-gray-500 text-[13px] font-normal mt-2">{{ detail }}</li>
                  </ol>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        sections: [
          {
            title: "Educations",
            items: [
              { name: "Bachelor's Computer Science", institution: "Royal University of Phnom Penh (2022 - 2025)", description: "A secondary school diploma is also known as a high school diploma, high school degree, or certificate of secondary education." },
              { name: "High School Diploma", institution: "Hun Sen Tropang Tnoat High School (2019 - 2021)", description: "A secondary school diploma is also known as a high school diploma, high school degree, or certificate of secondary education." },
              { name: "Secondary School Diploma", institution: "Hun Sen Tropang Tnoat High School (2016 - 2019)", description: "A secondary school diploma is also known as a high school diploma, high school degree, or certificate of secondary education." }
            ]
          },
          {
            title: "Software Skills",
            items: [
              { name: "Skills Basic", details: ["HTML", "CSS", "JavaScript", "Bootstrap", "PHP"] },
              { name: "Frameworks", details: ["Tailwind", "Angular", "Laravel PHP", "React [Medium]", "Vue [Medium]"] },
              { name: "Tools", details: ["GitHub", "Postman", "Docker", "MySQL & XAMPP", "Microsoft Word / Excel"] }
            ]
          },
          {
            title: "Experiences",
            items: [
              { name: "Frontend Developer", institution: "CamCyber ICT Solution | Phnom Penh (July 2024 - Jan 2025)", details: ["Developed and maintained responsive user-friendly interfaces using HTML and CSS.", "Collaborated with the development team to implement consistent designs.", "Assisted in troubleshooting and resolving frontend issues for optimal performance."] },
              { name: "Trainee Full Stack Development", institution: "CamCyber ICT Solution | Phnom Penh (Feb 2024 - May 2024)", details: ["Worked with PHP Laravel for the backend and Angular for frontend development.", "Developed web applications ensuring smooth integration between frontend and backend."] },
              { name: "Trainee Basic Web Design", institution: "CamCyber ICT Solution | Phnom Penh (June 2023 - Oct 2023)", details: ["Learning basic web development concepts with HTML, CSS, JavaScript, Bootstrap, PHP, SQL, and XAMPP.", "Focus on static web design and basic web application development."] }
            ]
          }
        ]
      };
    }
  };
  </script>
  