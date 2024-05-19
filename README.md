<h1>N-Tier Architecture Template</h1>

<p>Bu proje, .NET Core N-Tier mimarisi ile çalışan projeler için gerekli olan 4 adet Item Template içeren bir Visual Studio Extension (VSIX) sağlamaktadır. Bu extension, projelerinizde kullanabileceğiniz <code>Entity</code>, <code>Dto</code>, <code>Repository</code>, ve <code>ServiceHelper</code> şablonlarını içerir.</p>

<h2>İçindekiler</h2>
<ul>
    <li><a href="#setup">Kurulum</a></li>
    <li><a href="#usage">Kullanım</a></li>
    <li><a href="#templates">Şablonlar</a>
        <ul>
            <li><a href="#entity">Entity</a></li>
            <li><a href="#dto">Dto</a></li>
            <li><a href="#repository">Repository</a></li>
            <li><a href="#servicehelper">ServiceHelper</a></li>
        </ul>
    </li>
</ul>

<h2 id="setup">Kurulum</h2>
<ol>
    <li><strong>VSIX Dosyasını İndir</strong>: <a href="https://github.com/kullaniciadi/projeadi/releases">VisualStudio Marketplace</a> sayfasından en son sürümü indirin.</li>
    <li><strong>Kurulum</strong>: İndirdiğiniz <code>.vsix</code> dosyasına çift tıklayın ve Visual Studio'ya yükleyin.</li>
    <li><strong>Visual Studio'yu Yeniden Başlatın</strong>: Değişikliklerin geçerli olması için Visual Studio'yu yeniden başlatın.</li>
</ol>

<h2 id="usage">Kullanım</h2>
<ol>
    <li><strong>Yeni Item Ekleme</strong>:
        <ul>
            <li>Çözüm Gezgininden bir proje klasörüne sağ tıklayın.</li>
            <li><code>Add</code> > <code>New Item</code> seçeneğini seçin.</li>
            <li>Açılan pencerede <code>C# Items</code> > <code>ME Templates</code> içerisinden template seçin (<code>Entity</code>, <code>Dto</code>, <code>Repository</code>, <code>ServiceHelper</code>).</li>
            <li>Dosyanın ismini girin ve <code>Add</code> butonuna tıklayın.</li>
        </ul>
    </li>
</ol>
<img src="https://bugrame.com/images/me_template.gif" alt="ME Template" />


<h2 id="templates">Template'ler</h2>

<h3 id="entity">Entity</h3>
<p><code>Entity</code> şablonu genellikle veritabanı tablolarını temsil eder ve veri modelini tanımlar.</p>
<h4>Örnek Kullanım:</h4>
<pre><code>public class Product : BaseDto {
    &nbsp
}</code></pre>

<h3 id="dto">Dto</h3>
<p><code>Dto (Data Transfer Object)</code> şablonu genellikle veri aktarımı için kullanılan nesneleri oluşturmak için kullanılır.</p>
<h4>Örnek Kullanım:</h4>
<pre><code>public class ProductDto : BaseDto {
    &nbsp
}</code></pre>

<h3 id="repository">Repository</h3>
<p><code>Repository</code> şablonu veri erişim mantığını iş mantığından ayırır ve daha temiz bir mimari sağlar.</p>
<h4>Örnek Kullanım:</h4>
<pre><code>
public class ProductRepository : BaseRepository&lt;Product&gt; {
    public ProductRepository() { }
}</code></pre>


<h3 id="servicehelper">ServiceHelper</h3>
<p><code>ServiceHelper</code> şablonu, servis katmanında kullanılan yardımcı sınıfları oluşturmak için kullanılır. İş mantığını içerir ve servisler arasında kod tekrarını önler.</p>
<h4>Örnek Kullanım:</h4>
<pre><code>public class ProductService : BaseService&lt;ProductRepository, ProductDto, Product&gt; {
    public ProductService() { }
}
</code></pre>
