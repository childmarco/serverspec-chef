# serverspec-chef



vagrant init
vagrant plugin install vagrant-omnibus
Installing the 'vagrant-omnibus' plugin. This can take a few minutes...
Installed the plugin 'vagrant-omnibus (1.4.1)'!


curl -L https://www.opscode.com/chef/install.sh | sudo bash
sudo knife cookbook create ruby-env -o ./site-cookbooks/.

chikashi-no-MacBook-Pro:serverspec-chef niiyama$ git commit -m "add ruby env"
[master 7c61d18] add ruby env
 12 files changed, 293 insertions(+), 16 deletions(-)
 create mode 100644 site-cookbooks/hello/CHANGELOG.md
 create mode 100644 site-cookbooks/hello/README.md
 create mode 100644 site-cookbooks/hello/metadata.rb
 create mode 100644 site-cookbooks/hello/recipes/default.rb
 create mode 100644 site-cookbooks/ruby-env/CHANGELOG.md
 create mode 100644 site-cookbooks/ruby-env/README.md
 create mode 100644 site-cookbooks/ruby-env/attributes/default.rb
 create mode 100644 site-cookbooks/ruby-env/metadata.rb
 create mode 100644 site-cookbooks/ruby-env/recipes/default.rb
 create mode 100644 site-cookbooks/ruby-env/templates/default/.bash_profile.rb
chikashi-no-MacBook-Pro:serverspec-chef niiyama$
chikashi-no-MacBook-Pro:serverspec-chef niiyama$
chikashi-no-MacBook-Pro:serverspec-chef niiyama$
chikashi-no-MacBook-Pro:serverspec-chef niiyama$ git push origin master
Counting objects: 22, done.
Delta compression using up to 8 threads.
Compressing objects: 100% (17/17), done.
Writing objects: 100% (22/22), 3.55 KiB | 0 bytes/s, done.
Total 22 (delta 5), reused 0 (delta 0)
To git@github.com:childmarco/serverspec-chef.git
   b29b22e..7c61d18  master -> master
chikashi-no-MacBook-Pro:serverspec-chef niiyama$
chikashi-no-MacBook-Pro:serverspec-chef niiyama$
chikashi-no-MacBook-Pro:serverspec-chef niiyama$
chikashi-no-MacBook-Pro:serverspec-chef niiyama$
chikashi-no-MacBook-Pro:serverspec-chef niiyama$
chikashi-no-MacBook-Pro:serverspec-chef niiyama$ ll
total 16
drwxr-xr-x   6 niiyama  staff   204  7 11 00:17 .
drwxr-xr-x   7 niiyama  staff   238  7 10 22:58 ..
drwxr-xr-x  14 niiyama  staff   476  7 11 00:18 .git
-rw-r--r--   1 niiyama  staff   314  7 11 00:17 README.md
-rw-r--r--   1 niiyama  staff  2037  7 11 00:04 Vagrantfile
drwxr-xr-x   4 niiyama  staff   136  7 11 00:09 site-cookbooks
chikashi-no-MacBook-Pro:serverspec-chef niiyama$
chikashi-no-MacBook-Pro:serverspec-chef niiyama$
chikashi-no-MacBook-Pro:serverspec-chef niiyama$
chikashi-no-MacBook-Pro:serverspec-chef niiyama$
chikashi-no-MacBook-Pro:serverspec-chef niiyama$
chikashi-no-MacBook-Pro:serverspec-chef niiyama$ vagrant up
Bringing machine 'default' up with 'virtualbox' provider...
==> default: Box 'serverspec' could not be found. Attempting to find and install...
    default: Box Provider: virtualbox
    default: Box Version: >= 0
==> default: Adding box 'serverspec' (v0) for provider: virtualbox
    default: Downloading: https://github.com/2creatives/vagrant-centos/releases/download/v6.5.3/centos65-x86_64-20140116.box
==> default: Successfully added box 'serverspec' (v0) for 'virtualbox'!
There are errors in the configuration of this machine. Please fix
the following errors and try again:

VagrantPlugins::Omnibus::Config:
* The following settings shouldn't exist: chf_version


chikashi-no-MacBook-Pro:serverspec-chef niiyama$ vagrant up
Bringing machine 'default' up with 'virtualbox' provider...
==> default: Importing base box 'serverspec'...
==> default: Matching MAC address for NAT networking...
==> default: Setting the name of the VM: serverspec-chef_default_1468164137065_65940
==> default: The cookbook path '/Users/niiyama/infra_test/serverspec-chef/cookbooks' doesn't exist. Ignoring...
==> default: Fixed port collision for 22 => 2222. Now on port 2200.
==> default: Clearing any previously set network interfaces...
==> default: Preparing network interfaces based on configuration...
    default: Adapter 1: nat
    default: Adapter 2: hostonly
==> default: Forwarding ports...
    default: 22 => 2200 (adapter 1)
==> default: Running 'pre-boot' VM customizations...
==> default: Booting VM...
==> default: Waiting for machine to boot. This may take a few minutes...
    default: SSH address: 127.0.0.1:2200
    default: SSH username: vagrant
    default: SSH auth method: private key
    default:
    default: Vagrant insecure key detected. Vagrant will automatically replace
    default: this with a newly generated keypair for better security.
    default:
    default: Inserting generated public key within guest...
    default: Removing insecure key from the guest if its present...
    default: Key inserted! Disconnecting and reconnecting using new SSH key...
==> default: Machine booted and ready!
==> default: Checking for guest additions in VM...
==> default: [vagrant-hostsupdater] Checking for host entries
==> default: [vagrant-hostsupdater] Writing the following entries to (/etc/hosts)
==> default: [vagrant-hostsupdater]   192.168.56.160  infra-testing  # VAGRANT: fe7f8cd01e5549a385acee2bf734ab58 (default) / 6e42ed8e-51e2-44fe-b826-0745bf8e6423
==> default: [vagrant-hostsupdater] This operation requires administrative access. You may skip it by manually adding equivalent entries to the hosts file.
Password:
Sorry, try again.
Password:
==> default: Setting hostname...
==> default: Configuring and enabling network interfaces...
==> default: Mounting shared folders...
    default: /vagrant => /Users/niiyama/infra_test/serverspec-chef
    default: /tmp/vagrant-chef/d02387b09c6662eab9df690daf6c3078/cookbooks => /Users/niiyama/infra_test/serverspec-chef/site-cookbooks
==> default: Installing Chef 12.12.15 Omnibus package...
==> default: el 6 x86_64
==> default: Getting information for chef stable 12.12.15 for el...
==> default: downloading https://omnitruck-direct.chef.io/stable/chef/metadata?v=12.12.15&p=el&pv=6&m=x86_64
==> default:   to file /tmp/install.sh.3076/metadata.txt
==> default: trying curl...
==> default: sha1	67b7e152fc8440ceb2a9f027e3b2edc93d3759db
==> default: sha256	9c6455bd30568c639e19485837bacbd07972c8e9f5cc3831fba4bc415bed24ad
==> default: url	https://packages.chef.io/stable/el/6/chef-12.12.15-1.el6.x86_64.rpm
==> default: version	12.12.15

==> default: downloaded metadata file looks valid...
==> default: downloading https://packages.chef.io/stable/el/6/chef-12.12.15-1.el6.x86_64.rpm
==> default:   to file /tmp/install.sh.3076/chef-12.12.15-1.el6.x86_64.rpm
==> default: trying curl...
==> default: Comparing checksum with sha256sum...
==> default: Installing chef 12.12.15
==> default: installing with rpm...
==> default: warning:
==> default: /tmp/install.sh.3076/chef-12.12.15-1.el6.x86_64.rpm: Header V4 DSA/SHA1 Signature, key ID 83ef826a: NOKEY
==> default: Preparing...
==> default: ##################################################

==> default: chef
==> default: #
==> default: #
==> default: #
==> default: #
==> default: #
==> default: #
==> default: #
==> default: #
==> default: #
==> default: #
==> default: #
==> default: #
==> default: #
==> default: #
==> default: #
==> default: #
==> default: #
==> default: #
==> default: #
==> default: #
==> default: #
==> default: #
==> default: #
==> default: #
==> default: #
==> default: #
==> default: #
==> default: #
==> default: #
==> default: #
==> default: #
==> default: #
==> default: #
==> default: #
==> default: #
==> default: #
==> default: #
==> default: #
==> default: #
==> default: #
==> default: #
==> default: #
==> default: #
==> default: #
==> default: #
==> default: #
==> default: #
==> default: #
==> default: #
==> default: #

==> default: Thank you for installing Chef!
==> default: Running provisioner: chef_solo...
==> default: Detected Chef (latest) is already installed
Generating chef JSON and uploading...
==> default: Running chef-solo...
==> default: [2016-07-10T15:23:22+00:00] INFO: Started chef-zero at chefzero://localhost:8889 with repository at /tmp/vagrant-chef/d02387b09c6662eab9df690daf6c3078
==> default:   One version per cookbook
==> default:
==> default: [2016-07-10T15:23:22+00:00] INFO: Forking chef instance to converge...
==> default: [2016-07-10T15:23:22+00:00] INFO: *** Chef 12.12.15 ***
==> default: [2016-07-10T15:23:22+00:00] INFO: Platform: x86_64-linux
==> default: [2016-07-10T15:23:22+00:00] INFO: Chef-client pid: 3493
==> default: [2016-07-10T15:23:29+00:00] INFO: #<ChefZero::RestErrorResponse: 404: Object not found: chefzero://localhost:8889/nodes/infra-testing>
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-zero-4.7.1/lib/chef_zero/rest_base.rb:91:in `rescue in get_data'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-zero-4.7.1/lib/chef_zero/rest_base.rb:83:in `get_data'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-zero-4.7.1/lib/chef_zero/endpoints/rest_object_endpoint.rb:18:in `get'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-zero-4.7.1/lib/chef_zero/rest_base.rb:62:in `call'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-zero-4.7.1/lib/chef_zero/rest_router.rb:24:in `call'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-zero-4.7.1/lib/chef_zero/server.rb:664:in `block in app'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-zero-4.7.1/lib/chef_zero/server.rb:336:in `call'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-zero-4.7.1/lib/chef_zero/server.rb:336:in `handle_socketless_request'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-zero-4.7.1/lib/chef_zero/socketless_server_map.rb:87:in `request'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-zero-4.7.1/lib/chef_zero/socketless_server_map.rb:33:in `request'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/lib/chef/http/socketless_chef_zero_client.rb:154:in `request'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/lib/chef/http.rb:305:in `block in send_http_request'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/lib/chef/http.rb:336:in `block in retrying_http_errors'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/lib/chef/http.rb:334:in `loop'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/lib/chef/http.rb:334:in `retrying_http_errors'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/lib/chef/http.rb:299:in `send_http_request'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/lib/chef/http.rb:144:in `request'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/lib/chef/http.rb:111:in `get'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/lib/chef/node.rb:585:in `load'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/lib/chef/node.rb:569:in `find_or_create'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/lib/chef/policy_builder/dynamic.rb:72:in `load_node'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/lib/chef/client.rb:467:in `load_node'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/lib/chef/client.rb:269:in `run'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/lib/chef/application.rb:286:in `block in fork_chef_client'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/lib/chef/application.rb:274:in `fork'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/lib/chef/application.rb:274:in `fork_chef_client'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/lib/chef/application.rb:239:in `block in run_chef_client'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/lib/chef/local_mode.rb:44:in `with_server_connectivity'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/lib/chef/application.rb:227:in `run_chef_client'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/lib/chef/application/client.rb:456:in `sleep_then_run_chef_client'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/lib/chef/application/client.rb:443:in `block in interval_run_chef_client'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/lib/chef/application/client.rb:442:in `loop'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/lib/chef/application/client.rb:442:in `interval_run_chef_client'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/lib/chef/application/client.rb:426:in `run_application'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/lib/chef/application.rb:59:in `run'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/lib/chef/application/solo.rb:217:in `run'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/bin/chef-solo:25:in `<top (required)>'
==> default: /usr/bin/chef-solo:52:in `load'
==> default: /usr/bin/chef-solo:52:in `<main>'
==> default: [2016-07-10T15:23:29+00:00] INFO: HTTP Request Returned 404 Not Found: Object not found: chefzero://localhost:8889/nodes/infra-testing
==> default: [2016-07-10T15:23:29+00:00] INFO: Setting the run_list to ["recipe[env-ruby]"] from CLI options
==> default: [2016-07-10T15:23:29+00:00] INFO: Run List is [recipe[env-ruby]]
==> default: [2016-07-10T15:23:29+00:00] INFO: Run List expands to [env-ruby]
==> default: [2016-07-10T15:23:29+00:00] INFO: Starting Chef Run for infra-testing
==> default: [2016-07-10T15:23:29+00:00] INFO: Running start handlers
==> default: [2016-07-10T15:23:29+00:00] INFO: Start handlers complete.
==> default: [2016-07-10T15:23:29+00:00] INFO: HTTP Request Returned 404 Not Found: Object not found:
==> default: [2016-07-10T15:23:29+00:00] INFO: #<ChefZero::RestErrorResponse: 412: No such cookbook: env-ruby>
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-zero-4.7.1/lib/chef_zero/endpoints/environment_cookbook_versions_endpoint.rb:23:in `block in post'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-zero-4.7.1/lib/chef_zero/endpoints/environment_cookbook_versions_endpoint.rb:16:in `each'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-zero-4.7.1/lib/chef_zero/endpoints/environment_cookbook_versions_endpoint.rb:16:in `post'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-zero-4.7.1/lib/chef_zero/rest_base.rb:62:in `call'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-zero-4.7.1/lib/chef_zero/rest_router.rb:24:in `call'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-zero-4.7.1/lib/chef_zero/server.rb:664:in `block in app'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-zero-4.7.1/lib/chef_zero/server.rb:336:in `call'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-zero-4.7.1/lib/chef_zero/server.rb:336:in `handle_socketless_request'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-zero-4.7.1/lib/chef_zero/socketless_server_map.rb:87:in `request'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-zero-4.7.1/lib/chef_zero/socketless_server_map.rb:33:in `request'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/lib/chef/http/socketless_chef_zero_client.rb:154:in `request'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/lib/chef/http.rb:305:in `block in send_http_request'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/lib/chef/http.rb:336:in `block in retrying_http_errors'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/lib/chef/http.rb:334:in `loop'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/lib/chef/http.rb:334:in `retrying_http_errors'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/lib/chef/http.rb:299:in `send_http_request'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/lib/chef/http.rb:144:in `request'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/lib/chef/http.rb:127:in `post'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/lib/chef/policy_builder/expand_node_object.rb:204:in `sync_cookbooks'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/lib/chef/policy_builder/expand_node_object.rb:83:in `setup_run_context'
==> default: /opt/chef/embedded/lib/ruby/2.1.0/forwardable.rb:183:in `setup_run_context'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/lib/chef/client.rb:510:in `setup_run_context'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/lib/chef/client.rb:280:in `run'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/lib/chef/application.rb:286:in `block in fork_chef_client'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/lib/chef/application.rb:274:in `fork'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/lib/chef/application.rb:274:in `fork_chef_client'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/lib/chef/application.rb:239:in `block in run_chef_client'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/lib/chef/local_mode.rb:44:in `with_server_connectivity'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/lib/chef/application.rb:227:in `run_chef_client'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/lib/chef/application/client.rb:456:in `sleep_then_run_chef_client'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/lib/chef/application/client.rb:443:in `block in interval_run_chef_client'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/lib/chef/application/client.rb:442:in `loop'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/lib/chef/application/client.rb:442:in `interval_run_chef_client'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/lib/chef/application/client.rb:426:in `run_application'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/lib/chef/application.rb:59:in `run'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/lib/chef/application/solo.rb:217:in `run'
==> default: /opt/chef/embedded/lib/ruby/gems/2.1.0/gems/chef-12.12.15/bin/chef-solo:25:in `<top (required)>'
==> default: /usr/bin/chef-solo:52:in `load'
==> default: /usr/bin/chef-solo:52:in `<main>'
==> default: [2016-07-10T15:23:29+00:00] INFO: HTTP Request Returned 412 Precondition Failed: No such cookbook: env-ruby
==> default:
==> default: ================================================================================
==> default: Error Resolving Cookbooks for Run List:
==> default: ================================================================================
==> default:
==> default:
==> default: Missing Cookbooks:
==> default: ------------------
==> default: No such cookbook: env-ruby
==> default:
==> default:
==> default: Expanded Run List:
==> default: ------------------
==> default: * env-ruby
==> default:
==> default:
==> default: Platform:
==> default: ---------
==> default: x86_64-linux
==> default:
==> default:
==> default: [2016-07-10T15:23:29+00:00] ERROR: Running exception handlers
==> default: [2016-07-10T15:23:29+00:00] ERROR: Exception handlers complete
==> default: [2016-07-10T15:23:29+00:00] FATAL: Stacktrace dumped to /var/chef/cache/chef-stacktrace.out
==> default: [2016-07-10T15:23:29+00:00] FATAL: Please provide the contents of the stacktrace.out file if you file a bug report
==> default: [2016-07-10T15:23:29+00:00] ERROR: 412 "Precondition Failed"
==> default: [2016-07-10T15:23:29+00:00] FATAL: Chef::Exceptions::ChildConvergeError: Chef run process exited unsuccessfully (exit code 1)
Chef never successfully completed! Any errors should be visible in the
output above. Please fix your recipes so that they properly complete.
chikashi-no-MacBook-Pro:serverspec-chef niiyama$