Download the source code
Go to this Github repository and click on the green color "<> Code" button to download the code.
Unzip the downloaded file and remember the directory location. There will be a client and a server directory.
Store your OpenAI API key in the .env file
Change directory to your server directory.
Create a .env file using NotePad++ or any text editor that allows you to save in this format. Type the following lines into the file and save:
OPENAI_API_KEY="YOUR_OPENAI_API_KEY"
YOUR_OPENAI_ORG_KEY="YOUR_OPENAI_ORG_KEY"
PINECONE_API_KEY="YOUR_PINECONE_API_KEY"
PINECONE_ENV="Your_environment"

Instructions for server-side setup
In your server directory, fill out the config.yaml file with your Pinecone API key, index name, and environment.
Install the necessary Python packages by running the following command:

pip install -r requirements.txt
python app.py
npm install
npm run dev

WebCrawler

Prerequisites
Before you can build this AI model, you need to complete the following steps:

Follow the quickstart tutorial for OpenAI to install Python on your computer. You need a Python version between 7 and 10. OpenAI has not tested the platform on Python version 11 yet. Download version 10 from https://www.python.org/downloads/.

Set up an OpenAI API key. Follow the instructions on the API Keys page to retrieve your API key. Then, create a .env file in the root directory of your project with the following contents:

Usage
After you have completed the above steps, you can run the web-qa.py script to start the AI model. The script will prompt you to enter a URL for your website. Once you enter the URL, the model will crawl your website and generate embeddings for each page. You can then ask questions about the content on your website and the model will provide answers.

You will need the following before executing the file

import requests
import re
import urllib.request
from bs4 import BeautifulSoup
from collections import deque
from html.parser import HTMLParser
from urllib.parse import urlparse
import os
import pandas as pd
import tiktoken #remember to pip install tiktoken
import openai
from openai.embeddings_utils import distances_from_embeddings
import numpy as np
from openai.embeddings_utils import distances_from_embeddings, cosine_similarity


