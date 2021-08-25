<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>FuVoicePack</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>


  <div class="keys">
    <div data-key="65" class="key">
      <kbd>A</kbd>
      <span class="sound">救</span>
    </div>
    <div data-key="83" class="key">
      <kbd>S</kbd>
      <span class="sound">真的欸</span>
    </div>
    <div data-key="68" class="key">
      <kbd>D</kbd>
      <span class="sound">倒讚倒讚幫</span>
    </div>
    <div data-key="70" class="key">
      <kbd>F</kbd>
      <span class="sound">拉打拉打</span>
    </div>
    <div data-key="71" class="key">
      <kbd>G</kbd>
      <span class="sound">這裡超多等下</span>
    </div>
    <div data-key="72" class="key">
      <kbd>H</kbd>
      <span class="sound">誰偷射我</span>
    </div>
    <div data-key="74" class="key">
      <kbd>J</kbd>
      <span class="sound">要爆炸了</span>
    </div>
    <div data-key="75" class="key">
      <kbd>K</kbd>
      <span class="sound">維克托欸</span>
    </div>
    <div data-key="76" class="key">
      <kbd>L</kbd>
      <span class="sound">嗚唷</span>
    </div>
  </div>

  <audio data-key="65" src="sounds/help.mp3"></audio>
  <audio data-key="83" src="sounds/indeed.mp3"></audio>
  <audio data-key="68" src="sounds/dislike.mp3"></audio>
  <audio data-key="70" src="sounds/pullhit.mp3"></audio>
  <audio data-key="71" src="sounds/somany.mp3"></audio>
  <audio data-key="72" src="sounds/whothefuckshotme.mp3"></audio>
  <audio data-key="74" src="sounds/gonnabomb.mp3"></audio>
  <audio data-key="75" src="sounds/victor!.mp3"></audio>
  <audio data-key="76" src="sounds/wooyo.mp3"></audio>


<script>
  function removeTransition(e) {
    if (e.propertyName !== 'transform') return;
    e.target.classList.remove('playing');
  }

  function playSound(e) {
    const audio = document.querySelector(`audio[data-key="${e.keyCode}"]`);
    const key = document.querySelector(`div[data-key="${e.keyCode}"]`);
    if (!audio) return;

    key.classList.add('playing');
    audio.currentTime = 0;
    audio.play();
  }

  const keys = Array.from(document.querySelectorAll('.key'));
  keys.forEach(key => key.addEventListener('transitionend', removeTransition));
  window.addEventListener('keydown', playSound);
</script>


</body>
</html>
