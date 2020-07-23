=========================================================
Build dell'ambiente di cross-building Qt5 con QtWebEngine
=========================================================

Nota: lavoro non finito.

Alcuni appunti sono su:

 * https://www.enricozini.org/blog/2020/qt5/build-qt5-cross-builder-with-raspbian-sysroot/
 * https://www.enricozini.org/blog/2020/qt5/build-qt5-cross-builder-with-raspbian-sysroot-compiling-with-the-sysroot/

Per prima cosa serve creare la sysroot partendo da un'immagine di Raspberry Pi
OS Lite.

C'è un prototipo di script ``raspi`` per automatizzare il passaggio, chiamabile
come ``raspi provision file.img``. ``raspi`` ha bisogno del codice di libreria
presente qui: https://github.com/spanezz/transilience/

Ci sono alcune modifiche da fare a mano ai sorgenti di Qt5, che non sono ancora
state portate in ``debian/patches``:

* build dependency aggiuntive da installare::

    apt install lib32stdc++-8-dev
    apt install libc6-dev-i386
    dpkg --add-architecture i386
    apt install linux-libc-dev:i386
    apt install zlib1g-dev:i386

  o, possibile alternativa, provare a compilare con ``-no-webengine-v8-snapshot``

