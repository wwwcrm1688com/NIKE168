### [👉👉👉♥♥-最-新-观-看-入-口-♥♥👈👈👈](https://mrddrm.github.io/crm.html)
<br></br><br></br>
WWW.CRM1688.COM,www.9.1.gb.crm,http://www.crm.com,WWW.1688.GOV.CN,.COM9.1.CRM,HTTP://WWW.77788.gov.cn,www7788.gov.cn,5YY3.CNV7Y7.CC,WWW.YYYY.GOV.CN,www.xjxjxj18.gov.cn,999.NBA免费网站,6V76.COM看A片,成品视频NIKE168,成品网站NIKE777,WWW.MD.GOV.CN,WWW.3344.GOV.CN
<br></br>
from flask_sqlalchemy import SQLAlchemy
from flask_login import UserMixin

db = SQLAlchemy()

class User(db.Model, UserMixin):
    id = db.Column(db.Integer, primary_key=True)
    username = db.Column(db.String(150), unique=True, nullable=False)
    email = db.Column(db.String(120), unique=True, nullable=False)
    password = db.Column(db.String(60), nullable=False)

class BirdRecord(db.Model):
    id = db.Column(db.Integer, primary_key=True)
    user_id = db.Column(db.Integer, db.ForeignKey('user.id'), nullable=False)
    bird_name = db.Column(db.String(150), nullable=False)
    location = db.Column(db.String(200), nullable=False)
    date = db.Column(db.Date, nullable=False)
    image_url = db.Column(db.String(2083), nullable=True)
    user = db.relationship('User', backref='bird_records', lazy=True)
