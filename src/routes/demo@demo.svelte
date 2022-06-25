<script>
  let htmlContent = '';
  fetch('./demo.html')
    .then((response) => {
      console.dir(response);
      return response.text();
    })
    .then((html) => {
      htmlContent = html;
    });
</script>

{@html htmlContent}
