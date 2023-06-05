<script lang="ts">
  import { onMount } from "svelte";

  const responses: string[] = [
    "Looks good to me!",
    "Yep, it works",
    "Ayy, it's alive!",
    "To the moon 🚀",
    "Big Brain Energy 💡",
    "Achievement Unlocked: Internet Connected 🏆",
    "Error 404: Common Sense Not Found",
    "This ain't your grandma's website 👵🚫",
    "Domain Flex 💪",
    "Adding this to my résumé",
    "Smells like online spirit",
    "Trust me, I'm an engineer",
    "Good news! It's not a Rickroll!",
    "Download more RAM? Done.",
    "The prophecy has been fulfilled!",
    "Told you it's working 💅",
    "Reality check: It's WORKING!",
    "It's 🔥 fam!",
    "Why, hello there, General Web-obi! ✋",
    "I'm not a robot, I swear",
  ];

  let randomResponse: string = "";

  function diceRoll() {
    return Math.floor(Math.random() * 15) === 1; // The probability is 1/15
  }

  onMount(() => {
    randomResponse = diceRoll()
      ? responses[Math.floor(Math.random() * responses.length)]
      : "Yes";
  });
</script>

<svelte:head>
  <title>ThisDomain.Works?</title>
</svelte:head>

<div class="flex h-screen flex-col justify-between">
  <!-- Yes -->
  <div class="grid place-items-center h-full">
    <p class="text-5xl font-semibold text-center">
      {randomResponse}
      <!-- In the case JS is disabled -->
      <noscript> Yes </noscript>
    </p>
  </div>

  <!-- Footer -->
  <footer class="grid place-items-center h-16 bg-gray-100">
    <!-- Link to github -->
    <a
      href="https://github.com/Wolfhound905/thisdomainworks"
      target="_blank"
      rel="noopener noreferrer"
      class="flex justify-center items-center"
    >
      <img src="/github-mark.svg" alt="Github" class="w-8 h-8" />
      <p class="font-semibold font-mono text-xl pl-2">@Wolfhound905</p>
    </a>
  </footer>
</div>
