+++
date = '{{ .Date }}'
draft = false
title = '{{ replace .File.ContentBaseName "-" " " | title }}'
description = ''
[params]
    image = ''
    author = 'Vincent Buchner'
    updated_at = '{{ .Date }}'
+++