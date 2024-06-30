---
layout: page
title: The Missing Semester of Your CS Education
nositetitle: true
---

Kelas-kelas ini mengajarkan Anda semua tentang topik-topik tingkat lanjut dalam Ilmu Komputer, mulai dari _operating system_ hingga _machine learning_, tetapi ada satu topik penting yang jarang dibahas,
dan sering kali diserahkan kepada siswa untuk mencari tahu sendiri: kemahiran dengan
dengan kakas mereka. Kami akan mengajarkan Anda cara menguasai _command line_, menggunakan
editor teks yang kuat, menggunakan fitur-fitur canggih dari sistem kontrol versi (_version control system_), dan banyak lagi!

Siswa menghabiskan ratusan jam menggunakan alat-alat ini selama masa pendidikan mereka
pendidikan mereka (dan ribuan selama karir mereka), jadi masuk akal untuk membuat
pengalaman yang lancar dan tanpa hambatan. Menguasai alat-alat ini tidak
tidak hanya memungkinkan Anda menghabiskan lebih sedikit waktu untuk mencari tahu cara membengkokkan alat Anda keinginan Anda, tetapi juga memungkinkan Anda memecahkan masalah yang sebelumnya tampak
yang sebelumnya tampak sangat rumit.

Baca mengenai [motivasi hadirnya kelas ini](/about/).

# Schedule

{% comment %}
**Lecture**: 35-225, 2pm--3pm<br>
**Office hours**: 32-G9 lounge, 3pm--4pm (every day, right after lecture)
{% endcomment %}

<ul>
{% assign lectures = site['2020'] | sort: 'date' %}
{% for lecture in lectures %}
    {% if lecture.phony != true %}
        <li>
        <strong>{{ lecture.date | date: '%-m/%d/%y' }}</strong>:
        {% if lecture.ready %}
            <a href="{{ lecture.url }}">{{ lecture.title }}</a>
        {% else %}
            {{ lecture.title }} {% if lecture.noclass %}[no class]{% endif %}
        {% endif %}
        </li>
    {% endif %}
{% endfor %}
</ul>

Video recordings of the lectures are available [on
YouTube](https://www.youtube.com/playlist?list=PLyzOVJj3bHQuloKGG59rS43e29ro7I57J).

# About the class

**Staff**: This class is co-taught by [Anish](https://www.anishathalye.com/), [Jon](https://thesquareplanet.com/), and [Jose](http://josejg.com/).<br>
**Questions**: Email us at [missing-semester@mit.edu](mailto:missing-semester@mit.edu).

# Selain MIT

Kami juga telah membagikan kelas ini di luar MIT dengan harapan orang lain dapat
mendapatkan manfaat dari sumber daya ini. Anda dapat menemukan tulisan dan berdiskusi di

 - [Hacker News](https://news.ycombinator.com/item?id=22226380)
 - [Lobsters](https://lobste.rs/s/ti1k98/missing_semester_your_cs_education_mit)
 - [/r/learnprogramming](https://www.reddit.com/r/learnprogramming/comments/eyagda/the_missing_semester_of_your_cs_education_mit/)
 - [/r/programming](https://www.reddit.com/r/programming/comments/eyagcd/the_missing_semester_of_your_cs_education_mit/)
 - [Twitter](https://twitter.com/jonhoo/status/1224383452591509507)
 - [YouTube](https://www.youtube.com/playlist?list=PLyzOVJj3bHQuloKGG59rS43e29ro7I57J)

{% comment %}
Lihat URL lainnya:

- https://news.ycombinator.com/item?id=27154577
- https://news.ycombinator.com/item?id=34934216
- https://www.reddit.com/r/learnprogramming/comments/nca1v3/mit_the_missing_semester_of_your_cs_education/
- https://www.reddit.com/r/compsci/comments/eyywv8/the_missing_semester_of_your_cs_education_from_mit/
- https://www.reddit.com/r/programming/comments/io7nq3/the_missing_semester_of_your_cs_education_mit/
- https://twitter.com/MIT_CSAIL/status/1349766980413263873
- https://twitter.com/MIT_CSAIL/status/1481676163491659780
- https://twitter.com/MIT_CSAIL/status/1581313961093484545
{% endcomment %}

# Terjemahan

- [Chinese (Simplified)](https://missing-semester-cn.github.io/)
- [Chinese (Traditional)](https://missing-semester-zh-hant.github.io/)
- [Japanese](https://missing-semester-jp.github.io/)
- [Korean](https://missing-semester-kr.github.io/)
- [Portuguese](https://missing-semester-pt.github.io/)
- [Russian](https://missing-semester-rus.github.io/)
- [Serbian](https://netboxify.com/missing-semester/)
- [Spanish](https://missing-semester-esp.github.io/)
- [Turkish](https://missing-semester-tr.github.io/)
- [Vietnamese](https://missing-semester-vn.github.io/)
- [Arabic](https://missing-semester-ar.github.io/)
- [Italian](https://missing-semester-it.github.io/)
- [Persian](https://missing-semester-fa.github.io/)
- [German](https://missing-semester-de.github.io/)
- [Bengali](https://missing-semester-bn.github.io/)
- [Indonesia](https://missing-semester-id.github.io/)

Catatan: ini adalah tautan eksternal ke terjemahan komunitas. Kami tidak memastikan secara seksama.

Apakah Anda membuat terjemahan dari kelas ini? 
Kirimkan [pull request](https://github.com/missing-semester/missing-semester/pulls) sehingga kami dapat menambahkannya ke dalam daftar!

## Ucapan Terima Kasih

Kami berterima kasih kepada Elaine Mello, Jim Cain, dan [MIT Open Learning](https://openlearning.mit.edu/) yang telah memungkinkan kami untuk
merekam video kuliah; Anthony Zolnik dan [MIT
AeroAstro](https://aeroastro.mit.edu/) untuk peralatan A/V; dan Brandi Adams dan
[MIT EECS](https://www.eecs.mit.edu/) yang telah mendukung kelas ini.

---

<div class="small center">
<p><a href="https://github.com/missing-semester/missing-semester">Source code</a>.</p>
<p>Licensed under CC BY-NC-SA.</p>
<p>See <a href="/license/">here</a> for contribution &amp; translation guidelines.</p>
</div>
