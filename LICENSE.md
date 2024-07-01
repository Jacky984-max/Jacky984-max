#!/bin/bash

# Directorio local a respaldar
SOURCE_DIR="/ruta/a/tu/directorio"

# Directorio de destino en Google Drive
DESTINATION_DIR="/ruta/a/tu/carpeta/de/google/drive"

# Comando rsync para sincronizar los archivos
rsync -avz --delete "$SOURCE_DIR" "$DESTINATION_DIR"
@echo off

REM Directorio local a respaldar
set SOURCE_DIR="C:\ruta\a\tu\directorio"

REM Directorio de destino en Dropbox
set DESTINATION_DIR="C:\ruta\a\tu\carpeta\de\dropbox"

REM Comando robocopy para copiar los archivos
robocopy %SOURCE_DIR% %DESTINATION_DIR% /mir /fft /xo
# Directorio donde se descargan los archivos (cambia según tu configuración)
$sourceDir = "C:\Usuarios\TuUsuario\Descargas"

# Directorios de destino según tipo de archivo
$imageDir = "C:\Usuarios\TuUsuario\Imágenes"
$docDir = "C:\Usuarios\TuUsuario\Documentos"
$musicDir = "C:\Usuarios\TuUsuario\Música"
$videoDir = "C:\Usuarios\TuUsuario\Vídeos"
$otherDir = "C:\Usuarios\TuUsuario\Otros"

# Verificar si los directorios de destino existen, si no, crearlos
if (!(Test-Path $imageDir)) { New-Item -ItemType Directory -Path $imageDir }
if (!(Test-Path $docDir)) { New-Item -ItemType Directory -Path $docDir }
if (!(Test-Path $musicDir)) { New-Item -ItemType Directory -Path $musicDir }
if (!(Test-Path $videoDir)) { New-Item -ItemType Directory -Path $videoDir }
if (!(Test-Path $otherDir)) { New-Item -ItemType Directory -Path $otherDir }

# Obtener todos los archivos en el directorio de origen
$files = Get-ChildItem -Path $sourceDir

# Recorrer cada archivo y moverlo al directorio correspondiente según la extensión
foreach ($file in $files) {
    $extension = $file.Extension.ToLower()
    switch ($extension) {
        ".jpg", ".png", ".gif", ".bmp" { Move-Item -Path $file.FullName -Destination $imageDir -Force }
        ".docx", ".pdf", ".txt", ".xlsx" { Move-Item -Path $file.FullName -Destination $docDir -Force }
        ".mp3", ".wav", ".flac" { Move-Item -Path $file.FullName -Destination $musicDir -Force }
        ".mp4", ".avi", ".mkv" { Move-Item -Path $file.FullName -Destination $videoDir -Force }
        default { Move-Item -Path $file.FullName -Destination $otherDir -Force }
    }
}
# Directorio donde se descargan los archivos (cambia según tu configuración)
$sourceDir = "C:\Usuarios\TuUsuario\Descargas"

# Directorios de destino según tipo de archivo
$imageDir = "C:\Usuarios\TuUsuario\Imágenes"
$docDir = "C:\Usuarios\TuUsuario\Documentos"
$musicDir = "C:\Usuarios\TuUsuario\Música"
$videoDir = "C:\Usuarios\TuUsuario\Vídeos"
$otherDir = "C:\Usuarios\TuUsuario\Otros"

# Verificar si los directorios de destino existen, si no, crearlos
if (!(Test-Path $imageDir)) { New-Item -ItemType Directory -Path $imageDir }
if (!(Test-Path $docDir)) { New-Item -ItemType Directory -Path $docDir }
if (!(Test-Path $musicDir)) { New-Item -ItemType Directory -Path $musicDir }
if (!(Test-Path $videoDir)) { New-Item -ItemType Directory -Path $videoDir }
if (!(Test-Path $otherDir)) { New-Item -ItemType Directory -Path $otherDir }

# Obtener todos los archivos en el directorio de origen
$files = Get-ChildItem -Path $sourceDir

# Recorrer cada archivo y moverlo al directorio correspondiente según la extensión
foreach ($file in $files) {
    $extension = $file.Extension.ToLower()
    switch ($extension) {
        ".jpg", ".png", ".gif", ".bmp" { Move-Item -Path $file.FullName -Destination $imageDir -Force }
        ".docx", ".pdf", ".txt", ".xlsx" { Move-Item -Path $file.FullName -Destination $docDir -Force }
        ".mp3", ".wav", ".flac" { Move-Item -Path $file.FullName -Destination $musicDir -Force }
        ".mp4", ".avi", ".mkv" { Move-Item -Path $file.FullName -Destination $videoDir -Force }
        default { Move-Item -Path $file.FullName -Destination $otherDir -Force }
    }
}
