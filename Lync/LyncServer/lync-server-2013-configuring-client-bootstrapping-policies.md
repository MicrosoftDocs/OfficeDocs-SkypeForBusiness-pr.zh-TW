---
title: Lync Server 2013：設定用戶端引導原則
description: Lync Server 2013：設定用戶端引導原則。
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
ms.openlocfilehash: 3c03a9f7954d42f128dd6ae96296069ae5a515e9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545629"
---
# <a name="configuring-client-bootstrapping-policies-in-lync-server-2013"></a>在 Lync Server 2013 中設定用戶端引導原則

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

群組原則管理主控台 (GPMC) ，而群組原則物件編輯器是您用來管理群組原則的工具。 隨附于 Office 群組原則系統管理範本（Lync)  (2013）和 adml (ADML) 系統管理範本，其中包含您為網域中的 [群組原則] 物件所設定的登錄型原則設定。 ADML 檔案是特定語言對 ADMX 檔案的補充。 每個 ADMX 和 ADML 檔案都包含單一 Office 應用程式的原則設定。 如需詳細資訊，請參閱 Office 2013 檔中的「Office 2013 系統管理範本檔案 (ADMX，ADML) 」 <https://go.microsoft.com/fwlink/p/?linkid=267516> 。

對於 Lync 2013，您應該考慮在使用者第一次登入伺服器之前，先考慮一些用戶端引導原則。 例如，用戶端應使用的預設伺服器及安全性模式，直到登入完成為止。 您可以使用群組原則在使用者的電腦登錄中建立這些設定，然後再登入，並開始從伺服器接收帶內布建設定。 下表列出 Lync 2013 可使用的群組原則設定。

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
 (ConfigurationMode) </p></td>
<td><p>指定 Lync 2013 如何識別登入期間使用的傳輸和伺服器。 在此設定中，您可以指定下列專案：</p>
<ul>
<li><p>ServerAddressExternal：指定從外部防火牆外部連線時，用戶端和同盟連絡人所使用的伺服器名稱或 IP 位址。</p></li>
<li><p>ServerAddressInternal：指定用戶端從組織防火牆內部連線時所使用的伺服器名稱或 IP 位址。</p></li>
<li><p>Transport：指定傳輸控制通訊協定 (TCP) 或傳輸層安全性 (TLS) 。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>其他支援的伺服器版本<br />
 (ConfiguredServerCheckValues) </p></td>
<td><p>指定除了預設所支援的伺服器版本之外，Lync Server 2013 會登入的伺服器版本名稱清單，並以分號分隔。</p></td>
</tr>
<tr class="odd">
<td><p>停用自動上傳失敗記錄 (DisableAutomaticSendTracing) </p></td>
<td><p>自動將登入失敗記錄上傳至 Lync Server 進行分析。 登入成功時，不會自動上傳記錄。 若未設定此原則，則會發生下列情況：</p>
<dl>
<dt><span></span></dt>
<dd><p>對於 Lync Online 使用者：可自動上傳登錄失敗記錄。</p>
</dd>
<dt><span></span></dt>
<dd><p>對於 Lync 內部部署使用者：上傳之前向使用者顯示確認對話方塊。</p>
</dd>
</dl>
<p>停用此設定時，會自動將 Lync 內部部署和 Lync Online 使用者的登入記錄上傳至 Lync Server。 啟用此設定時，將不會自動上傳登入記錄。</p></td>
</tr>
<tr class="even">
<td><p>停用 SIP 連線的 HTTP 回退<br />
 (DisableHttpConnect) </p></td>
<td><p>當 TLS 或 TCP 無法使用時，禁止 Lync 伺服器嘗試使用 HTTP 連線到伺服器。 依預設，Lync 會先使用 TLS 或 TCP 嘗試連線至伺服器，如果兩個傳輸方法都沒有成功，Lync 會嘗試使用 HTTP 進行連線。 使用此原則可停用後援 HTTP 連線嘗試。</p></td>
</tr>
<tr class="odd">
<td><p>需要登入認證<br />
 (DisableNTCredentials) </p></td>
<td><p>需要使用者提供 Lync 的登入認證，而不會在登入 SIP 伺服器期間自動使用 Windows 認證。</p></td>
</tr>
<tr class="even">
<td><p>停用伺服器版本檢查<br />
 (DisableServerCheck) </p></td>
<td><p>如果您將此原則設為1，請在登入前，禁止 Lync 檢查伺服器名稱及版本。 根據預設，Lync 會在登入前進行這些檢查。</p></td>
</tr>
<tr class="odd">
<td><p>啟用使用 BITS 下載通訊錄服務檔案<br />
 (EnableBitsForGalDownload) </p></td>
<td><p>可讓 Lync 使用後臺智慧傳輸服務 (BITS) 下載通訊錄服務檔案。</p></td>
</tr>
<tr class="even">
<td><p>設定 SIP 安全性模式<br />
 (EnableSIPHighSecurityMode) </p></td>
<td><p>可讓 Lync 更安全地傳送和接收立即訊息。 這個原則對 Windows .NET 或 Microsoft Exchange Server 服務沒有任何作用。</p>
<p>如果您未設定此原則設定，Lync 可以使用任何傳輸。 不過，如果它不使用 TLS，而且伺服器驗證使用者，Lync 必須使用 NTLM 或 Kerberos 驗證。</p></td>
</tr>
<tr class="odd">
<td><p>全域通訊錄下載初始延遲<br />
 (GalDownloadInitialDelay) </p></td>
<td><p>會指定在 (GAL) 中下載全域通訊清單之前的時間週期。 預設值為60分鐘，這表示伺服器會延遲下載 GAL 檔案，其隨機期限介於0到60分鐘之間。</p></td>
</tr>
<tr class="even">
<td><p>防止使用者執行 Microsoft Lync<br />
 (PreventRun) </p></td>
<td><p>防止使用者執行 Lync。 您可在「電腦設定」和「使用者設定」中設定此原則設定，但系統會優先使用「電腦設定」中的原則設定。</p></td>
</tr>
<tr class="odd">
<td><p>允許儲存使用者密碼<br />
 (SavePassword) </p></td>
<td><p>可讓 Lync 儲存密碼。</p></td>
</tr>
<tr class="even">
<td><p>設定 SIP 壓縮模式<br />
 (SipCompression) </p></td>
<td><p>指定何時開啟 SIP 壓縮。 根據預設，以配接器速度啟用 SIP 壓縮。 請注意，設定此原則可能導致登入時間變長。</p></td>
</tr>
<tr class="odd">
<td><p>受信任的網域清單<br />
 (TrustModelData) </p></td>
<td><p>列出不符合客戶 SIP 網域首碼的信任網域。</p></td>
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
<td><p>Lync Server 2013 頻帶內布建</p></td>
</tr>
<tr class="even">
<td><p>第</p></td>
<td><p>HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</p></td>
</tr>
<tr class="odd">
<td><p>個</p></td>
<td><p>HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</p></td>
</tr>
<tr class="even">
<td><p>4 </p></td>
<td><p>Lync 2013 中的 [Lync-選項] 對話方塊</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-define-group-policy-settings-by-using-the-lync-2013-administrative-template-files"></a>使用 Lync 2013 系統管理範本檔案定義群組原則設定

1.  建立根層級的資料夾，以包含所有語言中立的 ADMX 檔案。 例如，在此位置的網域控制站上建立中央存放區的根資料夾：
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    <div>
    

    > [!NOTE]  
    > 此程式假設您要管理網域中的多部電腦。 在此情況下，您可以將範本儲存在網域主控站的 Sysvol 資料夾中的中央存放區。 這會為網域系統管理範本提供複製的中央儲存位置。

    
    </div>

2.  為您要使用的每一種語言建立子資料夾。 這些子資料夾將會包含特定語言的 ADML 資源檔。 例如，在此位置，為美國英文 (EN-US) 建立子資料夾：
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`

</div>

</div>

<span> </span>

</div>

</div>

</div>

