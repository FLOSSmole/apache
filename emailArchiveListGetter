"""
Created on Tue Jun 27 10:54:27 2017

@author: jhartmann
"""
from bs4 import BeautifulSoup
import sys
try:
    import urllib.request as urllib2
except ImportError:
    import urllib2
    
hdr = {'User-Agent': 'Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.11 (KHTML, like Gecko) Chrome/23.0.1271.64 Safari/537.11',
       'Accept': 'text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8',
       'Accept-Charset': 'ISO-8859-1,utf-8;q=0.7,*;q=0.3',
       'Accept-Encoding': 'none',
       'Accept-Language': 'en-US,en;q=0.8',
       'Connection': 'keep-alive'}
       
archiveHome = 'http://mail-archives.apache.org/mod_mbox/'       
req = urllib2.Request(archiveHome,headers=hdr)
archiveListPage = urllib2.urlopen(req).read()

# Get all email archive titles

mainSoup = BeautifulSoup(archiveListPage, 'html.parser')
allUrl = mainSoup.find_all('a')
schemaList = []
for url in allUrl:
    isolatedName = ''
    url = str(url.get('href'))
    if url != 'None':
        isolatedName = url.split('/')[0]
        schemaList.append(isolatedName)
        
# schemaList contains all of the project names that will need a schema. ther should be 358 different schema            

    
