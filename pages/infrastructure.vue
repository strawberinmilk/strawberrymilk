<template>
  <div :id="$style.main">
    <h1>rin;宅のインフラについて語りたい</h1>
    <h3>インターネット環境について</h3>
    <p>インターネット環境は図にすると以下のようになります</p>
    <img src="/internet.png" />
    <P>
      光ファイバーはGMO光アクセスで引きました。
      でもv6プラスは速いけどポート開放とかで難があることも開通後にわかりました。
    </P>
    <p>
      そこで私がとった選択は、もう一本プロバイダを契約してそちらでPPPoEセッションを張ってしまおうというものです。
      ONU直下にハブを置くことはできるのかわからなかったですが、 調べるうちに<a
        ref="noreferrer noopener"
        target="_blank"
        href="https://www.interlink.or.jp/service/flets/multisession.html"
        >インターリンク</a
      >のサイトが参考にしできることがわかりました。
    </p>
    <p>
      初めのうちはルータを分けて完全に別系統にしていましたが、
      PCがデスクトップになりSSHやRDPで外からアクセスしたい需要が発生したため二重ルータの問題が発生しないよう気を付けつつ図のような構成に落ち着きました。
    </p>
    <p>
      正味最近はこういうページを作るよりもインフラを弄る方が楽しくなってしまい、公開しているものが徐々にしょうもなくなっている実情に焦っています。
    </p>

    <h3>自作ルータについて</h3>
    <p>
      自作ルータは
      <a
        ref="noreferrer noopener"
        target="_blank"
        href="https://www.shop-inverse.com"
        >ショップインバース</a
      >
      で買ったジャンクのDELL製のPCです。別途購入したNICを二枚刺し、LANポートが9つあるPCとして動作させています。
      OSはOPNsenseで完全にルータ特化マシンとして活躍しています。
    </p>
    <img src="/opnsense.jpg" />
    <table>
      <tr>
        <th>装置名</th>
        <th>スペック</th>
      </tr>
      <tr>
        <td>CPU</td>
        <td>Core i3-2100</td>
      </tr>
      <tr>
        <td>RAM</td>
        <td>4GB</td>
      </tr>
      <tr>
        <td>ROM</td>
        <td>SATASSD 100GB</td>
      </tr>
    </table>

    <h3>公開用サーバについて</h3>
    <p>
      公開用サーバは
      <a
        ref="noreferrer noopener"
        target="_blank"
        href="https://twitter.com/akibajunks"
        >アキバジャンクス</a
      >
      さんの2022年初売りで入手したジャンクmateさんです。RAMを追加し清掃などを行い常時稼働させていますがそろそろ燃えそうで怖いです。
    </p>
    <img src="/mate.jpg" />
    <table>
      <tr>
        <th>装置名</th>
        <th>スペック</th>
      </tr>
      <tr>
        <td>CPU</td>
        <td>Core i3-2120</td>
      </tr>
      <tr>
        <td>RAM</td>
        <td>4GB</td>
      </tr>
      <tr>
        <td>ROM</td>
        <td>SATASSD 120GB</td>
      </tr>
    </table>
    <p>
      OSとしてubuntuを入れたのち<a
        ref="noreferrer noopener"
        target="_blank"
        href="https://dokku.com"
        >dokku</a
      >を導入し、オンプレでこのサイトなどをホスティングしています。
    </p>
    <p>
      dokkuは、ちょっとしたサイトを簡単に公開でき、LetsEncryptによるSSL化やpostgresを簡単に用意できるなど、非常に便利です。
      デプロイも git push dokku main
      のようにできて、非常に簡単で家に一つあるだけで生活が変ります。
    </p>

    <h3>宅内サーバについて</h3>
    <p>
      宅内サーバにはルータ機と同じく<a
        ref="noreferrer noopener"
        target="_blank"
        href="https://www.shop-inverse.com"
        >ショップインバース</a
      >
      さんで購入したNEC製のジャンクPCを採用しています。
    </p>
    <p>
      このマシンにはOSはubuntu、SambaとMinecraft
      Serverが導入されており、主にNASとして使用しております。
    </p>
    <p>
      かつてはこのマシンが公開用サーバ兼宅内サーバでしたがインターリンク導入を機に宅内専用となった経緯があり一番性能が強いです。
      この子を公開用にしたかったけど、NASのお引越しが面倒で別途用意してという形に落ち着きました。
    </p>

    <table>
      <tr>
        <th>装置名</th>
        <th>スペック</th>
      </tr>
      <tr>
        <td>CPU</td>
        <td>Core i5-2400</td>
      </tr>
      <tr>
        <td>RAM</td>
        <td>8GB</td>
      </tr>
      <tr>
        <td>ROM(ブート用)</td>
        <td>SATASSD 120GB</td>
      </tr>
      <tr>
        <td>ROM(NAS用)</td>
        <td>SATAHDD 2TB RAID1</td>
      </tr>
    </table>

    <h3>メイン機について</h3>
    <p>
      ついでに紹介。<a
        ref="noreferrer noopener"
        target="_blank"
        href="https://shop.tsukumo.co.jp"
        >ツクモ</a
      >
      さんで購入した自作PCを採用しています。
    </p>
    <p>
      このマシンにはOSはWindows
      11が導入されており、プログラミングからゲームまで幅広く使っています。
    </p>
    <p>
      Ubuntuをデュアルブートでインストールできる余地を残して組んであり、将来的には入れます。
    </p>

    <table>
      <tr>
        <th>装置名</th>
        <th>スペック</th>
      </tr>
      <tr>
        <td>CPU</td>
        <td>Ryzen 7 5700X</td>
      </tr>
      <tr>
        <td>RAM</td>
        <td>32GB</td>
      </tr>
      <tr>
        <td>ROM(ブート用)</td>
        <td>M.2SSD 2TB</td>
      </tr>
      <tr>
        <td>ROM(データ用)</td>
        <td>M.2SSD 1TB</td>
      </tr>
      <tr>
        <td>GPU</td>
        <td>GeForce RTX 3060 ti</td>
      </tr>
      <tr>
        <td>電源</td>
        <td>FSP 650W</td>
      </tr>
      <tr>
        <td>マザボ</td>
        <td>ASUS TUF GAMING B550-PLUS</td>
      </tr>
    </table>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'Infrastructure',
})
</script>

<style module>
#main {
  text-align: center;
  width: 70%;
  margin: 0 auto;
}

table {
  margin: 0 auto;
}

img {
  width: 100%;
}
</style>
