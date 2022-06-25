<script>
</script>

<div class="bg-animation">
  <div class="overlay">
    <div class="welcome">
      <h1>BORDER WALLETS</h1>
      <h2>Introducing a new way to quickly and reliably memorise Bitcoin seed phrases.</h2>
    </div>
    <div class="btn-container">
      <a href="/docs" class="btn btn-primary">Learn More</a>
      <a href="/docs/download-the-entropy-grid-generator" class="btn">Download EGG</a>
    </div>
  </div>
</div>

<h2>TLDR:</h2>
<p>
  Memorising Bitcoin seed phrases (typically between 12 and 24 randomised words) can be difficult.
  By exploiting a phenomenon known as the Picture Superiority Effect, we have devised a way make it
  significantly easier to do this - using user-generated patterns.
</p>
<p>
  To assist with this process and make it robust and secure, we have created a tool (the Entropy
  Grid Generator - or EGG) that randomises all 2048 Bitcoin BIP39 seed words and presents them back
  to users as unique, randomised matrices; we call these 'Entropy Grids'.
</p>
<p>
  When users generate their Entropy Grid, they apply their own choice of pattern(s) to them, therein
  unlocking each applicable seed word to create uniquely memorable wallets; we call these 'Border
  Wallets'.
</p>
<p>
  For more information on how we do this, to access our Entropy Grid Generator (EGG), and for
  instructions on how to create your own Border Wallet, read our <a href="/docs">Documentation</a> section
  in detail.
</p>
<p>
  If you are already familiar with our Docs section, you can download the EGG <a
    href="/docs/download-the-entropy-grid-generator">here</a
  >.
</p>

<style>
  .bg-animation {
    width: 100%;
    height: 100vh;
    background-color: white;
    position: relative;
    margin-top: -1rem;
    margin-left: -1rem;
    background-image: url(./BorderWallet.gif);
    background-repeat: no-repeat;
    background-position: center center;
    background-size: contain;
  }
  .overlay {
    color: var(--accent-color);
    text-shadow: 2px 2px 5px black;
    text-align: center;
    position: absolute;
    width: 100%;
    height: 100%;
    padding: 10%;
    background-color: #00000055;
  }
  .btn-container {
    margin: 0 auto;
    padding: 1rem;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
    position: absolute;
    top: 70%;
    width: 80%;
  }
  .btn {
    border: 1px solid var(--accent-color);
    max-width: 20rem;
    padding: 1rem;
    border-radius: 1rem;
    background-color: var(--header-bg-color);
    text-decoration: none;
    cursor: pointer;
    text-align: center;
    text-shadow: none;
  }
  .btn-primary {
    color: var(--header-bg-color);
    border-color: var(--header-bg-color);
    background-color: var(--accent-color);
  }
  .welcome {
    background-color: #383e42dd;
    padding: 1rem;
    border-radius: 2rem;
    margin-bottom: 1rem;
  }
</style>
