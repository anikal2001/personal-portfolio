<script context="module">
  import {
    authorsStore,
    fetchAuthors,
    fetchSocials,
    socialsStore,
  } from '$stores/site-metadata'
  import LinkedinIcon from './linkedin-icon.svelte'
  import GithubIcon from './github-icon.svelte'
  import YouTubeIcon from './you-tube-icon.svelte'

  fetchAuthors()
  fetchSocials()
</script>

<script>
  const { githubUrl, linkedinUrl } = $socialsStore
  const { name: AuthorName } = $authorsStore
</script>

<footer
  class="p-10 footer bg-primary text-primary-content footer-center"
>
  <div class="grid grid-flow-col gap-4">
    <a class="link link-hover" href="/projects">Portfolio</a>
    <a class="link link-hover" href="/posts">Blog</a>
    <a class="link link-hover" href="/about">About</a>
  </div>
  <div>
    <div class="grid grid-flow-col gap-4">
      <a href={githubUrl}>
        <GithubIcon />
      </a>
      <a href={linkedinUrl}>
        <LinkedinIcon />
      </a>
    </div>
  </div>
  <div>
    <p>
      Copyright &copy; {`${new Date().getFullYear()}`} - All right reserved
      {AuthorName}
    </p>
  </div>
</footer>
