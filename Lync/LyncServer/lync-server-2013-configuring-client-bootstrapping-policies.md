---
title: Lync Server 2013：設定用戶端引導原則
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
ms.openlocfilehash: 8258063645267fb12801548ddfdeae1b4ef7c795
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758321"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-client-bootstrapping-policies-in-lync-server-2013"></a>在 Lync Server 2013 中設定用戶端引導原則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

群組原則管理主控台（GPMC）和群組原則物件編輯器是您用來管理群組原則的工具。 Office 群組原則管理範本隨附于 Lync 2013 與 adml （ADML）系統管理範本，其中包含您針對網域中的 [群組原則] 物件所設定的登錄型原則設定。 ADML 檔案是對 ADMX 檔案的語言特定補充。 每個 ADMX 與 ADML 檔案都包含單一 Office 應用程式的原則設定。 如需詳細資訊，請參閱 Office 2013 檔中的「Office 2013 管理範本檔案（ADMX、ADML） <http://go.microsoft.com/fwlink/p/?linkid=267516>」。

在 Lync 2013 中，有數個用戶端的引導原則，您必須先考慮在使用者第一次登入伺服器前進行設定。 例如，用戶端在登入完成之前應該要使用的預設伺服器和安全模式。 您可以使用群組原則在使用者的電腦註冊表中建立這些設定，然後再登入並開始從伺服器接收帶外的提供設定設定。 下表列出 Lync 2013 可用的群組原則設定。

### <a name="group-policy-settings-for-lync-2013"></a>Lync 2013 的群組原則設定

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>群組原則設定</th>
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>指定伺服器<br />
(ConfigurationMode)</p></td>
<td><p>指定 Lync 2013 如何識別登入期間要使用的傳輸與伺服器。 在此設定中，您指定下列各項：</p>
<ul>
<li><p>ServerAddressExternal：指定從外部防火牆外部連線時，用戶端和同盟連絡人所使用的伺服器名稱或 IP 位址。</p></li>
<li><p>ServerAddressInternal：指定用戶端從組織的防火牆內連線時所使用的伺服器名稱或 IP 位址。</p></li>
<li><p>傳輸：指定傳輸控制通訊協定（TCP）或傳輸層安全性（TLS）。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>支援的其他伺服器版本<br />
(ConfiguredServerCheckValues)</p></td>
<td><p>指定伺服器版本名稱的清單，除了預設支援的伺服器版本之外，還會使用 Lync Server 2013 將登入的分號來分隔。</p></td>
</tr>
<tr class="odd">
<td><p>停用登入失敗記錄的自動上傳（DisableAutomaticSendTracing）</p></td>
<td><p>自動將登入失敗記錄上傳到 Lync Server 進行分析。 如果登入成功，則不會自動上傳任何記錄。 如果未設定此原則，就會發生下列情況：</p>
<dl>
<dt><span></span></dt>
<dd><p>Lync Online 使用者：系統會自動上傳登入失敗記錄。</p>
</dd>
<dt><span></span></dt>
<dd><p>對於 Lync 內部部署使用者： [上傳] 之前，會向使用者顯示確認對話方塊。</p>
</dd>
</dl>
<p>停用此設定時，系統會針對 Lync 內部部署和 Lync Online 使用者自動將登入記錄上傳到 Lync Server。 啟用此設定時，不會自動上傳登入記錄。</p></td>
</tr>
<tr class="even">
<td><p>停用 SIP 連線的 HTTP 回退<br />
(DisableHttpConnect)</p></td>
<td><p>如果 TLS 或 TCP 無法使用，則禁止 Lync Server 嘗試使用 HTTP 連線到伺服器。 根據預設，Lync 會先嘗試使用 TLS 或 TCP 連線到伺服器，如果這些傳輸方法都沒有成功，Lync 會嘗試使用 HTTP 進行連線。 使用此原則來停用回退 HTTP 連線嘗試。</p></td>
</tr>
<tr class="odd">
<td><p>需要登入認證<br />
(DisableNTCredentials)</p></td>
<td><p>要求使用者為 Lync 提供登入認證，而不是在登入 SIP 伺服器期間自動使用 Windows 認證。</p></td>
</tr>
<tr class="even">
<td><p>停用伺服器版本檢查<br />
(DisableServerCheck)</p></td>
<td><p>如果您將此原則設定為1，則會在登入前，避免 Lync 檢查伺服器名稱和版本。 根據預設，Lync 會先進行這些檢查，然後才能登入。</p></td>
</tr>
<tr class="odd">
<td><p>啟用 BITS 以下載通訊錄服務檔<br />
(EnableBitsForGalDownload)</p></td>
<td><p>讓 Lync 使用背景智慧傳輸服務（BITS）下載通訊錄服務檔案。</p></td>
</tr>
<tr class="even">
<td><p>設定 SIP 安全模式<br />
(EnableSIPHighSecurityMode)</p></td>
<td><p>讓 Lync 能更安全地傳送及接收立即訊息。 此原則對 Windows .NET 或 Microsoft Exchange Server 服務沒有任何影響。</p>
<p>如果您未設定此原則設定，Lync 可以使用任何傳輸。 但如果它不使用 TLS，且伺服器驗證使用者的身份，Lync 必須使用 NTLM 或 Kerberos 驗證。</p></td>
</tr>
<tr class="odd">
<td><p>全域通訊錄下載初始延遲<br />
(GalDownloadInitialDelay)</p></td>
<td><p>指定在下載全域通訊清單（GAL）之前的時間週期。 預設值為60分鐘，表示伺服器會延遲下載 GAL 檔案，且隨機期間為0到60分鐘。</p></td>
</tr>
<tr class="even">
<td><p>防止使用者執行 Microsoft Lync<br />
(PreventRun)</p></td>
<td><p>防止使用者執行 Lync。 您可以在 [電腦設定] 和 [使用者設定] 底下設定此原則設定，但 [電腦設定] 底下的原則設定優先。</p></td>
</tr>
<tr class="odd">
<td><p>允許儲存使用者密碼<br />
(SavePassword)</p></td>
<td><p>啟用 Lync 來儲存密碼。</p></td>
</tr>
<tr class="even">
<td><p>設定 SIP 壓縮模式<br />
(SipCompression)</p></td>
<td><p>指定何時開啟 SIP 壓縮。 根據預設，SIP 壓縮會根據配接器速度而啟用。 請注意，設定此原則可能會增加登入時間。</p></td>
</tr>
<tr class="odd">
<td><p>受信任的網域清單<br />
TrustModelData</p></td>
<td><p>列出與客戶 SIP 網域的首碼不相符的信任網域。</p></td>
</tr>
</tbody>
</table>


在伺服器上設定的原則會優先于使用者設定的群組原則設定和用戶端選項。 下表摘要列出發生衝突時設定的優先順序順序。

### <a name="group-policy-precedence"></a>群組原則優先順序

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>高於</th>
<th>設定的位置或方法</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>Lync Server 2013 內布配</p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p>HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>HKEY_CURRENT_USER \SOFTWARE\Policies\Microsoft\Office\15.0\Lync</p></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p>Lync 2013 中的 [Lync-選項] 對話方塊</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-define-group-policy-settings-by-using-the-lync-2013-administrative-template-files"></a>使用 Lync 2013 系統管理範本檔案來定義群組原則設定

1.  建立根層級資料夾，以包含所有語言中立的 ADMX 檔案。 例如，在以下位置為網網域控制站上的中央存放區建立根資料夾：
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    <div>
    

    > [!NOTE]  
    > 這個程式假設您想要管理網域中的多部電腦。 在這種情況下，您會將範本儲存在主要網網域控制站上 Sysvol 資料夾中的中央存放區。 這會提供網域系統管理範本的複製中央儲存位置。

    
    </div>

2.  針對您要使用的每個語言建立子資料夾。 這些子資料夾將包含特定語言的 ADML 資源檔案。 例如，在此位置為美國英文（ZH-CN）建立子資料夾：
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`

</div>

</div>

<span> </span>

</div>

</div>

</div>

