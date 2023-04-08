---
layout: post
title: "expresiones regulares para parsear un RSS o XML con PHP"
date: "2008-04-24"
categories: php
tags: ["expresiones-regulares","librerias-y-funciones"]
coverImage: "url-regex-1.jpg"
published: true
---

![Expresiones Regulares para parsear un RSS en PHP](/assets/images/2008/url-regex-1.jpg)

En este post voy a explicar como eliminar un contenido determinado ya sea una imagen o una etiqueta HTML, que no queremos que salga cuando parseamos el RSS o XML mediante expresiones regulares con la funcion `preg_match`

<code> 
	preg_match(‘/<p id="desc">([^<]+)</p>/’,$array_videos[0][‘description’],$descripcion);
	if(strlen($descripcion[1]) > 70){ 
		$valor = substr($descripcion[1],0,70)."…";
	} else {
	$valor = $descripcion[1];
	} 
</code>

La funcion `preg_match` elimina de las etiquetas que queremos en este caso elimina todo el contenido y la etiqueta `<p id="desc">`

Despues recorta la cadena en 70 caracteres.
