Ant Design'in stil değişkenlerini nasıl değiştireceğiniz hakkında bilgi verebilirim.

Öncelikle, antd / antd-mobile klasörlerinde tüm stil değişkenlerine erişebilirsiniz.

İki seçenek mevcut:

Seçenek (Önerilen):
package.json dosyanızda "theme" alanını yapılandırarak değişiklik yapabilirsiniz. "theme" alanı ya bir nesne ya da dosya yolu olarak yapılandırılabilir.
Örnek olarak:

"theme": {
"primary-color": "#1088ae",
},
// ya da
"theme": "./theme.js",

Atölye yapısı kullanmalısınız (antd-init ve dva-cli bunu destekler). Farklı bir çerçeve kullanıyorsanız, modifyVars yapılandırmasını kullanarak özgün stil değişkenlerini değiştirebilirsiniz.

Dikkat edin, stil dosyaları less dosyası olarak yüklenmelidir. Babel-plugin-import stil özelliğinin doğru bir şekilde yapılandırıldığından emin olun.

Seçenek:
Ayrı bir less dosyası oluşturun ve burada istediğiniz değişkenleri ayarlayın. Daha sonra, bu dosyayı projenize dahil edebilirsiniz.
Örnek olarak:

@import "~antd/dist/antd.less";
@import "your-theme-file"; // Önceden tanımlanmış değişkenleri değiştirmek için kullanılır.

Dikkat: Bu yöntemin dezavantajı, tüm bileşenlerin stilini yüklemesi ve babel-plugin-import'in stil özelliği ile birlikte kullanılamamasıdır.