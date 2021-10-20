.. _aula:

##########
aula
##########

aula is an innovative participation concept that enables young people to actively participate in their schools and communities,.. 
With the help of an online platform and didactic support, aula promotes democratic practices and competencies. 


Installation
========

Frontend preparation
-------------

0. Before starting make shure that you are using node.js 14, above there are Problems to install the software

.. code-block:: bash

  [aula@betelgeuse ~]$ uberspace tools version use node 14
  Selected Node.js version 14
  The new configuration is adapted immediately. Minor updates will be applied automatically.
  [aula@betelgeuse ~]$  

1. Clone the frontend repository from https://gitlab.com/delibrium/aula-app.git

.. code-block:: bash

[aula@betelgeuse ~]$ git clone https://gitlab.com/delibrium/aula-app.git
[aula@betelgeuse ~]$

cd aula-app and install dependencies with npm i
I use npm audit fix fore some issues

change the base url with nano static/js/config.js to http://localhost:8082/api/

baseUrl = 'http://localhost:8082/api/'

change the BASE_API with nano config/prod.env.js to http://localhost:8082/api/

BASE_API: '"http://localhost:8082/api/"',

npm run-script build

Backend
----------------

You need a running instance of postgresql, see the guide in manual and lab for details

Clone the repository from https://gitlab.com/delibrium/delibrium-postgrest.git
git clone https://gitlab.com/delibrium/delibrium-postgrest.git

