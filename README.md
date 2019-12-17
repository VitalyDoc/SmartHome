#WebRepo
git status
git add .
git commit -am "init commit"
git push -u origin master


systemctl start docker
git config --global http.proxy http://student_iitk:student_iitk@172.17.106.1:3128
git config --global user.email "cdd777_91@mail.ru"
git config --global user.name "VitalyDoc"
git clone https://github.com/VitalyDoc/SmartHome.git
chmod 777 /srv
docker run -d -p 8080:80 -v /srv/:/usr/share/nginx/html nginx

https://www.leaderssl.ru/articles/223-apache-ssl-kak-nastroit-ssl-sertifikat-dlya-servera-apache - настройка ssl 

docker-compose
https://phptoday.ru/post/gotovim-lokalnuyu-sredu-docker-dlya-razrabotki-na-php готовим среду 

https://html5book.ru/html-tags/

import json
from odoo import http

class InfoTimetable(http.Controller):
    @http.route('/ajax/search_schedule', auth='public', type='json', csrf=False,  cors='*', methods=['POST', 'OPTIONS'])
    def AjaxSearchSchedule(self, query=''):
        if http.request.httprequest.method == 'OPTIONS':
            return ''

        objects = http.request.env['info.teachers_and_groups'].sudo().search([
            ('name', 'ilike', query)
        ], limit=10, order="name asc")
        return json.dumps(
            [{'id': obj.id, 'name': obj.name} for obj in objects]
        )
        
var xmlhttp = new XMLHttpRequest(); 
xmlhttp.open("POST", "http://localhost:8069/ajax/search_schedule");
xmlhttp.setRequestHeader("Content-Type", "application/json");
xmlhttp.send(JSON.stringify({query:"МИД18-01"}));
