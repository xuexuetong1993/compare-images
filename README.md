## cmpi.py

Крохотный скрипт-обертка для получения ssim и/или psnr двух изображений с помощью `ffmpeg`.

Написан ввиду нежелания автора устанавливать махину scikit-image со всеми её зависимостями ради одной столь банальной функции.

### Требования
* `python 3.4+ `
* `ffmpeg` в `PATH`

### Использование
#### Как отдельный скрипт
```
> cmpi.py -ref .\result.png -c .\20.jpeg
PSNR: 38.25
SSIM: 0.934374
```
__Примечание__: порядок референс-фото и модифицированного чисто условный:
```
> cmpi.py -ref .\20.jpeg -c .\result.png
PSNR: 38.25
SSIM: 0.934374
```
#### Как модуль
```
from cmpi import compare_images

ref = r'path\to\my\ref.png'
cmp = r'path\to\modified\image.jpg'

ssim_value = compare_images(ref, cmp, 'ssim')
psnr_value = compare_images(ref, cmp, 'psnr')
```
