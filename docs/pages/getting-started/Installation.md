# Installation
<h4 class="fw-light">Learn how to install Blueprint on your Pterodactyl instance.</h4><br/>

This marks the beginning of your journey with Blueprint, and maybe even Pterodactyl modding to begin with. We're thrilled to have you on board, let's get started!

Want to run Blueprint through Docker instead? Take a peek at the official <a href="https://github.com/BlueprintFramework/docker" class="text-primary-emphasis link-underline-opacity-0 link-underline"><i class="bi bi-box"></i> Blueprint Docker</a> repository [here](https://github.com/BlueprintFramework/docker).

<br><div class="bg-dark-subtle rounded-4 p-4 pb-3">
  <h4><i class="bi bi-rocket-takeoff-fill"></i> Prepare for liftoff</h4>
  <p class="pb-3">Before we start running a bunch of commands, we need to prepare a couple things. This won't take long!</p>

  <div class="bg-body rounded-3 p-3 mb-3">
    <h5><i class="bi bi-folder2-open"></i> What's your Pterodactyl path?</h5>
    <p class="mb-2 text-secondary"><small>We'll update the commands below to work for your specific installation</small></p>
    <p class="mb-2 text-secondary"><small>But if you didn't change the default Pterodactyl installation path, you don't need to change it here</small></p>
    <div class="input-group mb-3">
      <input type="text" id="dirPath" class="form-control" placeholder="/var/www/pterodactyl" aria-label="Pterodactyl default path" oninput="changethepath()">
    </div>
  </div>

  <div class="row">
    <!-- Node.js -->
    <div class="col col-12 col-md-6 pb-3">
      <b class="text-success-emphasis">
        <svg role="img" width="22" class="pb-1" fill="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><title>Node.js</title><path d="M11.998,24c-0.321,0-0.641-0.084-0.922-0.247l-2.936-1.737c-0.438-0.245-0.224-0.332-0.08-0.383 c0.585-0.203,0.703-0.25,1.328-0.604c0.065-0.037,0.151-0.023,0.218,0.017l2.256,1.339c0.082,0.045,0.197,0.045,0.272,0l8.795-5.076 c0.082-0.047,0.134-0.141,0.134-0.238V6.921c0-0.099-0.053-0.192-0.137-0.242l-8.791-5.072c-0.081-0.047-0.189-0.047-0.271,0 L3.075,6.68C2.99,6.729,2.936,6.825,2.936,6.921v10.15c0,0.097,0.054,0.189,0.139,0.235l2.409,1.392 c1.307,0.654,2.108-0.116,2.108-0.89V7.787c0-0.142,0.114-0.253,0.256-0.253h1.115c0.139,0,0.255,0.112,0.255,0.253v10.021 c0,1.745-0.95,2.745-2.604,2.745c-0.508,0-0.909,0-2.026-0.551L2.28,18.675c-0.57-0.329-0.922-0.945-0.922-1.604V6.921 c0-0.659,0.353-1.275,0.922-1.603l8.795-5.082c0.557-0.315,1.296-0.315,1.848,0l8.794,5.082c0.57,0.329,0.924,0.944,0.924,1.603 v10.15c0,0.659-0.354,1.273-0.924,1.604l-8.794,5.078C12.643,23.916,12.324,24,11.998,24z M19.099,13.993 c0-1.9-1.284-2.406-3.987-2.763c-2.731-0.361-3.009-0.548-3.009-1.187c0-0.528,0.235-1.233,2.258-1.233 c1.807,0,2.473,0.389,2.747,1.607c0.024,0.115,0.129,0.199,0.247,0.199h1.141c0.071,0,0.138-0.031,0.186-0.081 c0.048-0.054,0.074-0.123,0.067-0.196c-0.177-2.098-1.571-3.076-4.388-3.076c-2.508,0-4.004,1.058-4.004,2.833 c0,1.925,1.488,2.457,3.895,2.695c2.88,0.282,3.103,0.703,3.103,1.269c0,0.983-0.789,1.402-2.642,1.402 c-2.327,0-2.839-0.584-3.011-1.742c-0.02-0.124-0.126-0.215-0.253-0.215h-1.137c-0.141,0-0.254,0.112-0.254,0.253 c0,1.482,0.806,3.248,4.655,3.248C17.501,17.007,19.099,15.91,19.099,13.993z"/></svg>
        Node.js
      </b>
      <p>Blueprint depends on <b>Node.js v20</b> or later for rebuilding panel assets. You can install it through the commands below or by running <code>nvm install 20</code> if you are using Node version manager, we won't judge!</p>
      <pre><code class="language-bash">sudo apt-get install -y ca-certificates curl gnupg
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://deb.nodesource.com/gpgkey/nodesource-repo.gpg.key | sudo gpg --dearmor -o /etc/apt/keyrings/nodesource.gpg
echo "deb [signed-by=/etc/apt/keyrings/nodesource.gpg] https://deb.nodesource.com/node_20.x nodistro main" | tee /etc/apt/sources.list.d/nodesource.list
apt-get update
apt-get install -y nodejs</code></pre>
    </div>
    <!-- Yarn -->
    <div class="col col-12 col-md-6 pb-3">
      <b class="text-primary-emphasis">
        <svg role="img" width="22" class="pb-1" fill="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><title>Yarn</title><path d="M12 0C5.375 0 0 5.375 0 12s5.375 12 12 12 12-5.375 12-12S18.625 0 12 0zm.768 4.105c.183 0 .363.053.525.157.125.083.287.185.755 1.154.31-.088.468-.042.551-.019.204.056.366.19.463.375.477.917.542 2.553.334 3.605-.241 1.232-.755 2.029-1.131 2.576.324.329.778.899 1.117 1.825.278.774.31 1.478.273 2.015a5.51 5.51 0 0 0 .602-.329c.593-.366 1.487-.917 2.553-.931.714-.009 1.269.445 1.353 1.103a1.23 1.23 0 0 1-.945 1.362c-.649.158-.95.278-1.821.843-1.232.797-2.539 1.242-3.012 1.39a1.686 1.686 0 0 1-.704.343c-.737.181-3.266.315-3.466.315h-.046c-.783 0-1.214-.241-1.45-.491-.658.329-1.51.19-2.122-.134a1.078 1.078 0 0 1-.58-1.153 1.243 1.243 0 0 1-.153-.195c-.162-.25-.528-.936-.454-1.946.056-.723.556-1.367.88-1.71a5.522 5.522 0 0 1 .408-2.256c.306-.727.885-1.348 1.32-1.737-.32-.537-.644-1.367-.329-2.21.227-.602.412-.936.82-1.08h-.005c.199-.074.389-.153.486-.259a3.418 3.418 0 0 1 2.298-1.103c.037-.093.079-.185.125-.283.31-.658.639-1.029 1.024-1.168a.94.94 0 0 1 .328-.06zm.006.7c-.507.016-1.001 1.519-1.001 1.519s-1.27-.204-2.266.871c-.199.218-.468.334-.746.44-.079.028-.176.023-.417.672-.371.991.625 2.094.625 2.094s-1.186.839-1.626 1.881c-.486 1.144-.338 2.261-.338 2.261s-.843.732-.899 1.487c-.051.663.139 1.2.343 1.515.227.343.51.176.51.176s-.561.653-.037.931c.477.25 1.283.394 1.71-.037.31-.31.371-1.001.486-1.283.028-.065.12.111.209.199.097.093.264.195.264.195s-.755.324-.445 1.066c.102.246.468.403 1.066.398.222-.005 2.664-.139 3.313-.296.375-.088.505-.283.505-.283s1.566-.431 2.998-1.357c.917-.598 1.293-.76 2.034-.936.612-.148.57-1.098-.241-1.084-.839.009-1.575.44-2.196.825-1.163.718-1.742.672-1.742.672l-.018-.032c-.079-.13.371-1.293-.134-2.678-.547-1.515-1.413-1.881-1.344-1.997.297-.5 1.038-1.297 1.334-2.78.176-.899.13-2.377-.269-3.151-.074-.144-.732.241-.732.241s-.616-1.371-.788-1.483a.271.271 0 0 0-.157-.046z"/></svg>
        Yarn
      </b>
      <p>Pterodactyl uses Yarn for managing it's node modules, which we'll need to install as well.</p>
      <pre><code class="language-bash">npm i -g yarn</code></pre>
      <p>Navigate to your Pterodactyl (usually <code>/var/www/pterodactyl</code>) and run the following command to initialize dependencies:</p>
      <pre><code class="ptero-cmd language-bash">cd /var/www/pterodactyl
yarn</code></pre>
    </div>
    <!-- Additional dependencies -->
    <div class="col col-12">
      <b class="text-danger-emphasis">
        <i class="bi bi-boxes pb-1" style="font-size:22px;"></i>
        Additional dependencies
      </b>
      <p>We make use of some additional dependencies that might not come preinstalled with your distribution. For this example, we'll use <code>apt</code>. Commands may differ for distributions that are not Debian-based.</p>
      <pre><code class="language-bash">apt install -y zip unzip git curl wget</code></pre>
    </div>
  </div>
</div><br><br>

#### <i class="bi bi-stars"></i> Excited yet?
Whether you plan to use Blueprint for it's extensions, developer tools or both - we're so happy to see you! Within the next 15 minutes, you'll be able to install and develop extensions through and with the Blueprint framework.

<br>

#### <i class="bi bi-cloud-arrow-down-fill"></i> Download the latest release
Download the latest version of Blueprint onto your server by either downloading the latest release [from GitHub](https://github.com/BlueprintFramework/framework/releases/latest) or running the one-liner below (which will save the file as `release.zip`).

```bash
wget "$(curl -s https://api.github.com/repos/BlueprintFramework/framework/releases/latest | grep 'browser_download_url' | cut -d '"' -f 4)" -O release.zip
```

<br>

#### <i class="bi bi-file-zip-fill"></i> Extract release
Unarchive the release you downloaded in the previous step in your Pterodactyl folder.

```bash
mv release.zip /var/www/pterodactyl/release.zip
cd /var/www/pterodactyl
unzip release.zip
```

`unzip` might give you the choice to overwrite a file or not. When installing Blueprint, always overwrite existing Pterodactyl files, as they are needed for Blueprint to function.

<br>

#### <i class="bi bi-gear-fill"></i> Configuration
This step allows Blueprint to function and know where itself and Pterodactyl are located and which permissions to use. Create a file called `.blueprintrc` inside of your Pterodactyl directory to begin.

```bash
touch /var/www/pterodactyl/.blueprintrc
```

Modify the `$WEBUSER`, `$USERSHELL` and `$PERMISSIONS` values to match your environment. Provided below is the standard configuration for Debian-based systems, but you might need to make your own modifications.

```bash
echo \
'WEBUSER="www-data";
OWNERSHIP="www-data:www-data";
USERSHELL="/bin/bash";' >> /var/www/pterodactyl/.blueprintrc
```

<br>

#### <i class="bi bi-robot"></i> Let Blueprint do the rest
All that's left is giving `blueprint.sh` execute permissions and running it. Blueprint will then do the necessary commands to operate correctly automatically.

```bash
chmod +x blueprint.sh
bash blueprint.sh
```

Optionally you can enable Bash autocompletion by adding `source blueprint;` into your `.bashrc` (or `.zshrc` when using ZSH).

<br>

#### <i class="bi bi-check-circle-fill"></i> Mission complete!
Blueprint should now be installed onto your Pterodactyl panel which means you'll be able to start installing or developing extensions. To learn more about Blueprint's command line utility, run `blueprint -help`. If you like the project, please <a href="https://github.com/BlueprintFramework/framework" class="text-warning-emphasis">star</a> it on GitHub.

Get started with developing extensions through [this guide](?page=getting-started/Extension-development) or find new extensions on [the extension discovery list](https://blueprint.zip/browse). There is so much to discover, welcome to Blueprint.
