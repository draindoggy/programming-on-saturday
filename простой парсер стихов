import requests
from bs4 import BeautifulSoup
def getstih(url,indf):
    resp = requests.get(url)
    bs = BeautifulSoup(resp.text, "lxml")
    autor = bs.find('a', 'link-details')
    nazv_s = bs.find('header','head-content-poema').find_all('h1')
    stih = bs.find('article', 'block-poema').find_all('p')
    res = '\n'.join(x.text for x in nazv_s)
    res_ = '\n'.join(x.text for x in stih)
    lines = [res, autor.text, '', res_]
    fo = open('stih0000' + str(indf) + '.txt', 'w', encoding='utf-8')
    for line in lines:
        fo.write(line + '\n')
    fo.close()
f = open('ссылки на сайт.txt', 'r')
mas = f.read().split('\n')
indf = 1
for url in mas:
    if url!='':
        getstih(url,indf)
        indf = indf + 1
f.close()
