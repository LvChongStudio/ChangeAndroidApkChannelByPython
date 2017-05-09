#!/usr/bin/python #--coding:UTF-8--

import shutil 
import zipfile
import time
import os

#############################

#Describe : 签名、渠道号 
#D&P Author By : LvStudio
#Create Date : 2017-04-28 
#Modify Data : 2017-04-28

#############################

src_apk_name = 'app-debug.apk' # 要签名的
apk channel_file = 'channel.txt' # 渠道号文件（每行一个渠道号） 
target_home = 'signed_apk' 
prefix = 'app_lvstudio_' 
suffix = '.apk' 
current_time = time.strftime('%Y%m%d%H%M%S', time.localtime(time.time()))

print('signeding............')

f = open(channel_file) 
lines = f.readlines() 
f.close() 
os.mkdir(target_home)

for x in lines : 
    x = x.strip('\n') 
    target_name = prefix + x + '_' + current_time + suffix 
    print (src_apk_name + '=======' + target_name) target_file = target_home + '/' + target_name 
    shutil.copyfile(src_apk_name, target_file)
    with zipfile.ZipFile(target_file, mode='a') as zipFile: 
        zipFile.comment = bytes(x)

print('success............')
