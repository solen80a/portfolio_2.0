<script>
//import { PhoneIcon, MailIcon, LinkedInIcon, GitHubIcon } from "heroicons"

export default {
  name: 'ContactSection',
}
</script>

<template>
  <div class="contact">
    <h3>Sofia Lennbom</h3>        
        <a href= "+46705623461">+46(0)705 62 34 61</a>       
        <a href="sofialennbom@gmail.com">sofialennbom@gmail.com</a>        
  </div>
      <div class="footer-icons">
        <a href="https://www.linkedin.com/in/sofia-lennbom-91252195/" target="_blank" rel="noopener noreferrer">
          <LinkedInIcon className="linkedin" />
        </a>
        <a href="https://github.com/solen80a" target="_blank" rel="noopener noreferrer">
          <GitHubIcon className="github" />
        </a>
      </div>
</template>