# Ground-penetrating-radar (GPR) processing system (gprproc) and apps — companion source for the book

Design documents and code for the GPR processing system built in ***Toward a Million Lines IX — Building a Ground-Penetrating-Radar Processing App Yourself, from Raw Data to Depth Sections*** (Japanese title 『LLM で 100 万行のソフトウェア開発 IX — 生データから地中レーダーの処理アプリを自分で作る』; the book is in Japanese).

The processing system `gprproc` (Python) simulates, reads, preprocesses, focuses (migration), compares, and builds time-lapse differences and 3D volumes from ground-penetrating-radar data (impulse GPR and stepped-frequency GPR). Two Windows apps (Flutter) sit on top of it: a **processing app** and a **simulator**. **They are two separate apps**, each with its own EXE, folder and launcher. **The apps hold no processing of their own**: every button runs a `gprproc` command and reads the result files it writes. In this project **the design documents are the source of the code**.

## Download

**Ready-to-run apps and the source are on the [Releases](../../releases) page**, not in this repository. The release has three separate ZIPs:

| File | Contents |
|:---|:---|
| `gpr_exe.zip` | The two Windows apps, ready built (**Japanese screens**), in separate folders (`processor\` and `simulator\`), with a copy of the processing system and `.cmd` launchers |
| `gpr_exe_en.zip` | The same two apps (**English screens**) |
| `gpr.zip` | Design documents (`docs/`, Japanese, L1-L4, the source; `docs_en/`, the complete set for the English edition: L1-L3 translated into English, L4 the Japanese originals as is) in separate folders, the code (`src/gprproc/`, `app/`, and `src_en/`, a copy of the code and apps with English as the default language), and empty databases (`ledger/`, `product_db/`) |

The apps need Python 3.11 on your PC (see the README inside the ZIPs). There is **no APK** (the apps are Windows desktop apps). The apps are **not code-signed**, so Windows may warn you. Data, tests and processing results are not included; the simulator can make raw data of the same form as the data used in the book (MALA `rd3`/`rad` and SEG-Y), so the processing system can be run without downloading anything.

You are free to change the design documents and the code and compare the results.

---

## License

- **The author holds the copyright.**
- **The code is under the GNU General Public License v3.0 or later (GPL-3.0-or-later).** The full text is [`LICENSE`](LICENSE). **If you modify it and distribute it, you must publish the source under the same GPL-3.0-or-later terms.**
- **The design documents and the text are under the Creative Commons Attribution-ShareAlike 4.0 International license (CC BY-SA 4.0).** This covers `docs/`, `docs_en/`, the READMEs and the other written text of this repository, and the text of the matching book. See [`LICENSE-DOCS.md`](LICENSE-DOCS.md).
- **If you use them, say so.** State where it came from (the title of the book and the name of this repository) and keep the copyright notice. If you changed it, say that you changed it.
- **In this project the design documents are the source of the code.** When you publish something made from this code, **publish the design documents together with the code.**
- Third-party components (numpy, scipy, h5py, numba installed by `pip install .`; the Flutter engine inside the EXEs) remain under their own original licenses.
- The rights to the data used as examples in the book stay with the providers: Aberystwyth GPR data and the low-frequency GPR data (Zenodo), MERL-GPR (Mitsubishi Electric Research Laboratories), RIMFAX (NASA/PDS), SHARAD 3D (NASA/PDS), GPRbase ds021 (MDS, CC BY-NC-SA 4.0; the book shows only our own processed figures), and the synthetic 3D data set of Koyan, Roncoroni and Tronicke (Mendeley Data, CC BY 4.0). The data are not in this repository.
- Provided "as is", without warranty — as the GPL-3.0 text says.

## 著作権とライセンス

- **著作権は、著者にあります。**
- **コードは、GNU General Public License v3.0 以降（GPL-3.0-or-later）です。**全文は [`LICENSE`](LICENSE) です。**改変して配布するときは、同じ GPL-3.0 以降の条件で、ソースを公開する義務があります。**
- **設計書と文章は、Creative Commons 表示-継承 4.0 国際（CC BY-SA 4.0）です。**このリポジトリの `docs/`・`docs_en/`・README ほかの文章と、対応する本の文章が当たります。内容は [`LICENSE-DOCS.md`](LICENSE-DOCS.md) です。
- **使ったときは、使ったことを書いてください。**どこから使ったか（本の題名と、このリポジトリの名前）と、著作権の表示を、使った先に書いてください。直したときは、直したことも書いてください。
- **このプロジェクトでは、設計書がコードの源です。**コードを使って作ったものを公開するときは、**設計書も、コードと一緒に公開してください。**
- 第三者の部品（`pip install .` で入る numpy・scipy・h5py・numba、EXE の中の Flutter の engine）は、それぞれの元のライセンスのままです。
- 本の例に使ったデータの権利は、提供元に残ります: Aberystwyth の GPR のデータと低周波 GPR のデータ（Zenodo）、MERL-GPR（三菱電機研究所）、RIMFAX（NASA/PDS）、SHARAD 3D（NASA/PDS）、GPRbase ds021（MDS・CC BY-NC-SA 4.0。本に載せるのは私たちが処理した図だけ）、Koyan・Roncoroni・Tronicke の合成の 3D データ（Mendeley Data・CC BY 4.0）。データはこのリポジトリに含みません。
- 現状のまま（as is）提供します。保証はありません（GPL-3.0 の全文のとおりです）。
