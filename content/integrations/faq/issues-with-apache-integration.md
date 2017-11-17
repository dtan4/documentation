---
title: Issues with Apache Integration
kind: faq
customnav: integrationsnav
---

If you are having issues with your Apache integration, it is mostly like due to the Agent not being able to access your Apache status URL.  

Try running curl for the apache_status_url that you have in your apache.yaml file on your host, making sure to include your login credentials if applicable, to see if it outputs the stats correctly. If it does not, you'll need to change your permissions for the status URL to allow access from the host. You can read [this article](http://httpd.apache.org/docs/2.2/mod/mod_status.html) for more info.

If you still have issues, please [reach out to us](/help) with [a flare](/agent/faq/send-logs-and-configs-to-datadog-via-flare-command)