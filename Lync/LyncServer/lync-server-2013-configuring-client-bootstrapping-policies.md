---
title: Lync Server 2013： 設定用戶端啟動載入原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring client bootstrapping policies
ms:assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425941(v=OCS.15)
ms:contentKeyID: 48184031
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3827bf913c4108c1105376a6f178598a2fb45a06
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "41996648"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-client-bootstrapping-policies-in-lync-server-2013"></a>設定用戶端啟動載入 Lync Server 2013 中的原則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-21_

群組原則管理主控台 (GPMC) 和群組原則物件編輯器是您用來管理群組原則工具。 隨附於 Office 群組原則系統管理範本是 Lync 2013.admx (ADMX) 以及.adml (ADML) 系統管理範本，其中包含您的網域中的群組原則物件的登錄型原則設定。 ADML 檔案都是特定語言的互補 ADMX 檔案。 每個 ADMX 和 ADML 檔案包含單一 Office 應用程式的原則設定。 如需詳細資訊，請參閱 「 Office 2013 Administrative Template files （ADMX，ADML） 」 中的 Office 2013 文件<http://go.microsoft.com/fwlink/p/?linkid=267516>。

Lync 2013 的有幾個用戶端啟動載入原則，您應該考慮設定之前使用者登入伺服器第一次。 如範例、 預設伺服器和用戶端應該使用直到登入的安全性模式已完成。 您可以使用群組原則來建立使用者的電腦登錄中的這些設定之前他們登入，並開始接收來自伺服器的頻內佈建設定。 下表列出可供 Lync 2013 的群組原則設定。

### <a name="group-policy-settings-for-lync-2013"></a>Lync 2013 的群組原則設定

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>群組原則設定</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>指定伺服器<br />
(ConfigurationMode)</p></td>
<td><p>會指定如何 Lync 2013 識別 「 傳輸 」 和 「 登入期間所要使用的伺服器。 此設定，在您指定下列項目：</p>
<ul>
<li><p>ServerAddressExternal： 指定伺服器名稱或 IP 位址供用戶端及同盟連絡人從外部防火牆連線時。</p></li>
<li><p>ServerAddressInternal： 指定伺服器名稱或用戶端從組織防火牆內部連線時所使用的 IP 位址。</p></li>
<li><p>Transport： 指定傳輸控制通訊協定 (TCP) 或傳輸層安全性 (TLS)。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>支援的其他伺服器版本<br />
(ConfiguredServerCheckValues)</p></td>
<td><p>會指定以 Lync Server 2013 將登入，此外預設所支援的伺服器版本的分號分隔的伺服器版本名稱的清單。</p></td>
</tr>
<tr class="odd">
<td><p>停用自動上傳的登入失敗記錄 (DisableAutomaticSendTracing)</p></td>
<td><p>自動上傳登入失敗記錄至 Lync Server 進行分析。 如果登入成功自動上傳沒有記錄檔。 如果未設定此原則，會發生下列情況：</p>
<dl>
<dt><span></span></dt>
<dd><p>Lync Online 使用者： 登入失敗記錄會自動上傳。</p>
</dd>
<dt><span></span></dt>
<dd><p>針對 Lync 內部部署使用者： 上載之前對使用者顯示的確認對話方塊中，該資料。</p>
</dd>
</dl>
<p>停用此設定時，登入記錄檔會自動上傳到 Lync 內部部署和 Lync Online 使用者在 Lync 伺服器。 啟用此設定時，登入記錄檔會永遠不會自動上載。</p></td>
</tr>
<tr class="even">
<td><p>停用 HTTP 後援 SIP 連線<br />
(DisableHttpConnect)</p></td>
<td><p>Lync Server 可防止嘗試如果無法使用 TLS 或 TCP 使用 HTTP 連線至伺服器。 根據預設，Lync 第一次嘗試使用 TLS 或 TCP 連線至伺服器，然後 Lync 如果這些傳輸方法皆未成功，嘗試使用 HTTP 連線。 使用此原則可停用後援 HTTP 連線嘗試。</p></td>
</tr>
<tr class="odd">
<td><p>需要登入認證<br />
(DisableNTCredentials)</p></td>
<td><p>需要使用者以提供 Lync，而不是使用期間登入 SIP 伺服器的 Windows 認證自動登入認證。</p></td>
</tr>
<tr class="even">
<td><p>停用伺服器版本檢查<br />
(DisableServerCheck)</p></td>
<td><p>如果您將此原則設定為 1 時，可防止 Lync 登入前先檢查的伺服器名稱和版本。 根據預設，Lync 進行之前登入這類檢查。</p></td>
</tr>
<tr class="odd">
<td><p>啟用使用位元下載通訊錄服務檔案<br />
(EnableBitsForGalDownload)</p></td>
<td><p>可讓 Lync 使用背景智慧型傳送服務 (BITS) 下載通訊錄服務檔案。</p></td>
</tr>
<tr class="even">
<td><p>設定 SIP 安全性模式<br />
(EnableSIPHighSecurityMode)</p></td>
<td><p>可讓 Lync 傳送和接收立即訊息更安全的方式。 此原則具有不會影響 Windows.NET 或 Microsoft Exchange Server 服務。</p>
<p>如果您未設定此原則，Lync 可以使用任何傳輸。 但如果它不會使用 TLS 和 Lync server 進行驗證的使用者，如果必須使用 NTLM 或 Kerberos 驗證。</p></td>
</tr>
<tr class="odd">
<td><p>全域通訊錄下載初始延遲<br />
(GalDownloadInitialDelay)</p></td>
<td><p>指定的時間之前的全域通訊清單 (GAL) 下載，就會發生。 預設值為 60 分鐘，這表示伺服器延遲介於 0 到 60 分鐘的隨機期間 GAL 檔案下載。</p></td>
</tr>
<tr class="even">
<td><p>防止使用者執行 Microsoft Lync<br />
(PreventRun)</p></td>
<td><p>防止使用者執行 Lync。 您可在「電腦設定」和「使用者設定」中設定此原則設定，但系統會優先使用「電腦設定」中的原則設定。</p></td>
</tr>
<tr class="odd">
<td><p>允許儲存使用者密碼<br />
(SavePassword)</p></td>
<td><p>可讓 Lync 儲存密碼。</p></td>
</tr>
<tr class="even">
<td><p>設定 SIP 壓縮模式<br />
(SipCompression)</p></td>
<td><p>指定何時要開啟 [SIP 壓縮。 根據預設，會根據介面卡速度啟用 SIP 壓縮。 請注意，設定此原則可能導致登入時間變長。</p></td>
</tr>
<tr class="odd">
<td><p>受信任的網域清單<br />
(TrustModelData)</p></td>
<td><p>列出受信任的網域，不會符合客戶 SIP 網域的前置詞。</p></td>
</tr>
</tbody>
</table>


在伺服器上設定的原則優先於群組原則設定和使用者設定的用戶端選項。下表摘要列出當衝突發生時，設定的優先順序。

### <a name="group-policy-precedence"></a>群組原則優先順序

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Precedence</th>
<th>設定的位置或方法</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1 </p></td>
<td><p>Lync Server 2013 頻內佈建</p></td>
</tr>
<tr class="even">
<td><p>2 </p></td>
<td><p>HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</p></td>
</tr>
<tr class="odd">
<td><p>3 </p></td>
<td><p>HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</p></td>
</tr>
<tr class="even">
<td><p>4 </p></td>
<td><p>[Lync-Lync 2013 中的 [選項] 對話方塊</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-define-group-policy-settings-by-using-the-lync-2013-administrative-template-files"></a>若要使用 Lync 2013 系統管理範本檔案定義群組原則設定

1.  建立包含所有的非語言相關 ADMX 檔案的根層級資料夾。 例如，您的網域控制站，這個位置上建立集中存放區的根資料夾：
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    <div>
    

    > [!NOTE]  
    > 此程序假設您想要管理您網域中的多部電腦。 在此情況下，您可以儲存範本集中存放區中的主要網域控制站的 Sysvol 資料夾中。 此網域系統管理範本提供複製的中央儲存位置。

    
    </div>

2.  建立您要使用的每種語言的子資料夾。 這些子資料夾會包含語言專屬 ADML 資源檔案。 例如，在此位置建立美國英文 (EN-US) 的子資料夾：
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`

</div>

</div>

<span> </span>

</div>

</div>

</div>

