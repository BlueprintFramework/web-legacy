<div class="position-relative p-4 text-body bg-body border rounded-4 d-flex align-items-center">
  <div class="me-3">
    <i class="bi bi-book h2"></i>
  </div>
  <p class="me-3 my-0">
    Written by those who've walked the path. Want to improve our guides? Contribute and help build something awesome!
  </p>
  <a href="https://github.com/BlueprintFramework/web/tree/main/docs/pages/developing-extensions">
    <button class="btn btn-primary px-4 rounded-pill placeholder-wave" type="button">
      Contribute
    </button>
  </a>
</div><br>

# Admin views
<h4 class="fw-light">Learn the basics of extension admin pages.</h4><br/>

After setting up your development template (Barebones) [in the previous guide](?page=getting-started/Extension-development), you can now start writing an admin view.

The Barebones template includes two files by default, `conf.yml` and `view.blade.php`. We'll take a look at `conf.yml` later, but first, open `view.blade.php` and add the following code:

<div class="row container mb-2">
  <div class="col rounded-1 py-2" style="background-color: #282c34">
    <pre><code class="hljs language-html hl-escape"><p>
  This extension is called <b>{name}</b>.
  <code>{identifier}</code> is the identifier of this extension.
  The current version is <i>{version}</i>.
</p></code></pre>
    <div class="border-top mb-3 code-spacer"></div>
    <div class="overflow-scroll">
      <img src="../.assets/storage/docs/png/3.png">
    </div>
  </div>
</div>

You might have already noticed that `{name}`, `{identifier}` and `{version}` are replaced with the corresponding values automatically. These strings are referred to as [placeholders](?page=documentation/placeholders).

Right now, all lines are on the same row. This is due to how HTML is rendered in Blueprint’s admin view, as it doesn’t handle line breaks. We can fix this by adding `<br>` tags at the end of each line.

<div class="row container mb-2">
  <div class="col rounded-1 py-2" style="background-color: #282c34">
    <pre><code class="hljs language-xml hl-escape"><p>
  This extension is called <b>{name}</b>. <br>
  <code>{identifier}</code> is the identifier of this extension. <br>
  The current version is <i>{version}</i>. <br>
</p></code></pre>
    <div class="border-top mb-3 code-spacer"></div>
    <div class="overflow-scroll">
      <img src="../.assets/storage/docs/png/5.png">
    </div>
  </div>
</div>

This looks a bit plain, doesn't it? We can spice things up and add a bit of depth with box containers, a fancy title, and a much better user experience.

We can achieve this with the `box` CSS class, which is included in the Pterodactyl admin panel by default. To add a nice color alongside the box, you can make use of the following classes: <a class="text-primary">`box-primary`</a>, <a class="text-info">`box-info`</a>, <a class="text-success">`box-success`</a>, <a class="text-warning">`box-warning`</a> and <a class="text-danger">`box-danger`</a>.

Here's an example of how you can use these classes to enhance your admin view:

<div class="row container mb-2">
  <div class="col rounded-1 py-2" style="background-color: #282c34">
    <pre><code class="hljs language-xml hl-escape"><div class="box box-info">
  <div class="box-header with-border">
    <h3 class="box-title">My awesome box</h3>
  </div>
  <div class="box-body">
    <p>
      This extension is called <b>{name}</b>. <br>
      <code>{identifier}</code> is the identifier of this extension. <br>
      The current version is <i>{version}</i>. <br>
    </p>
  </div>
</div></code></pre>
    <div class="border-top mb-3 code-spacer"></div>
    <div class="overflow-scroll">
      <img src="../.assets/storage/docs/png/6.png">
    </div>
  </div>
</div><br>

You have now created your very own admin page through Blueprint. Try experimenting a bit with it, and once you are ready, move on to the next guide to learn how to create custom controllers for your extension.

<div class="btn-group docs-navigator" role="group" aria-label="Navigation" style="float: right">
  <a href="?page=getting-started/Extension-development" class="btn btn-dark bg-light-subtle border-0 rounded-start-pill">Previous</a>
  <a href="?page=developing-extensions/Custom-controllers" class="btn btn-dark bg-light-subtle border-0 rounded-end-pill">Next</a>
</div>
