fcitx-table-scjc6-colemak
==============================

Fcitx scjc6 code table for Colemak layout.

Remapped Fcitx's scjc6 code table from Qwerty to Colemak.

.. image:: https://i.imgur.com/j5MRsvX.png

Get vector diagram: http://frantle.deviantart.com/art/scjc6-diagram-for-Colemak-layout-649013748

Install
==============================

Put ``table/scjc6-colemak.conf`` and ``table/scjc6-colemak.mb`` to your Fcitx table directory. On Arch Linux it is ``/usr/share/fcitx/table/``.

You may want to write a little package for your system to keep things clean.

Usage
==============================

Activate ``scjc6-colemak`` input method on Fcitx and it's ready for you.

Why
==============================

Fcitx's scjc6 uses English letters to form code table. So Fcitx's layout switching cannot keep same word root(字根) at same key position across two layouts. Remapped code table fixes this problem.

Notes
==============================

If you are wondering how it is made out or want to convert another fcitx's input method's layout, this section may help.

This code table is directly made from Fcitx's scjc6 code table. Follow these steps:

.. code:: bash

    # copy Fcitx's ``scjc6.mb`` and `scjc6.conf` to whatever directory.
    cp /usr/share/fcitx/table/scjc6.{conf,mb} WHATEVER_DIRECTORY/
    cd WHATEVER_DIRECTORY/

    # get a text version code table.
    mb2txt scjc6.mb >scjc6.txt

    # convert code table
    convert-qwerty-to-colemak.js scjc6.txt
    # now we get ``scjc6-colemak.txt``

    # convert new table back to .mb
    txt2mb scjc6-colemak.txt scjc6-colemak.mb

    # rename .conf file,
    # adjust it's ``UniqueName``, ``Name`` and ``File`` sections
    # to appropriate values.
    mv scjc6.conf scjc6-colemak.conf

    # now ``scjc6-colemak.mb`` and ``scjc6-colemak.conf`` are our converted table.

License
==============================

`GNU GPL v2`_

.. _`GNU GPL v2`: https://www.gnu.org/licenses/old-licenses/gpl-2.0.html
