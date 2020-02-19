---
title: Lync Server 2013： 規劃雙因素驗證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for two-factor authentication
ms:assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308562(v=OCS.15)
ms:contentKeyID: 54973683
ms.date: 04/06/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b973a1eeb704788eb07e02afc502ac4bbe41544c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139274"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-two-factor-authentication-in-lync-server-2013"></a>規劃 Lync Server 2013 中的雙因素驗證

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015年-04-06_

以下是設定 Microsoft Lync Server 2013 環境以支援雙重要素驗證時的部署考量的清單。

<div>

## <a name="client-support"></a>用戶端支援

Lync Server 2013 的 Lync 2013 累計更新： 7 月 2013年桌面用戶端和行動裝置的所有用戶端目前支援雙重要素驗證。

</div>

<div>

## <a name="topology-requirements"></a>拓撲需求

客戶是我們強烈鼓勵讀者部署專用的 Lync Server 2013 使用 Lync Server 2013 的累計更新的雙因素驗證： 7 月 2013 Edge、 Director、 和使用者集區。 若要啟用 Lync 之使用者的被動驗證，就必須停用其他驗證方法的其他角色和服務，包括下列：


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>設定類型</th>
<th>服務類型</th>
<th>伺服器角色</th>
<th>若要停用的驗證類型</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Web 服務</p></td>
<td><p>WebServer</p></td>
<td><p>Director</p></td>
<td><p>Kerberos、 NTLM、 和憑證</p></td>
</tr>
<tr class="even">
<td><p>Web 服務</p></td>
<td><p>WebServer</p></td>
<td><p>前端</p></td>
<td><p>Kerberos、 NTLM、 和憑證</p></td>
</tr>
<tr class="odd">
<td><p>Proxy</p></td>
<td><p>EdgeServer</p></td>
<td><p>銳利</p></td>
<td><p>Kerberos 及 NTLM</p></td>
</tr>
<tr class="even">
<td><p>Proxy</p></td>
<td><p>註冊機構</p></td>
<td><p>前端</p></td>
<td><p>Kerberos 及 NTLM</p></td>
</tr>
</tbody>
</table>


除非在服務層級停用這些驗證類型，所有其他版本的 Lync 用戶端將無法登入成功之後雙因素驗證您的部署中，已啟用內。

</div>

<div>

## <a name="lync-service-discovery"></a>Lync 服務探索

由內部及/或外部的用戶端用來探索 Lync 服務應設定為解析為雙因素驗證未啟用 Lync server 的 DNS 記錄。 與此組態中，來自未啟用雙因素驗證的 Lync 集區的使用者將不需要輸入 pin 碼，以進行驗證，而從雙因素驗證已啟用的 Lync 集區的使用者都必須輸入其 pin 碼以進行驗證。

</div>

<div>

## <a name="exchange-authentication"></a>Exchange 驗證

已部署雙因素驗證 Microsoft exchange 的客戶可能會發現在 Lync 用戶端特定功能都無法使用。 這是目前的設計、 Lync 用戶端不支援雙重要素驗證取決於 Exchange 整合的功能。

</div>

<div>

## <a name="lync-contacts"></a>Lync 連絡人

Lync 使用者利用整合連絡人存放區功能設定會尋找值，其連絡人就無法再供之後登入雙因素驗證。

您應該使用**Invoke-csucsrollback** cmdlet 從整合連絡人存放區中移除現有的使用者連絡人，並將它們儲存在 Lync Server 2013 中，才能啟用雙因素驗證。

</div>

<div>

## <a name="skill-search"></a>技能搜尋

已設定的技能搜尋功能，其 Lync 環境中的客戶會尋找值，這項功能無法運作時 Lync 啟用的雙因素驗證。 這是經過設計，為 Microsoft SharePoint 目前不支援雙重要素驗證。

</div>

<div>

## <a name="lync-credentials"></a>Lync 認證

有許多涉及可能會影響使用者設定為使用雙因素驗證儲存的 Lync 認證的部署考量。

<div>

## <a name="deleting-saved-credentials"></a>刪除儲存的認證

桌面用戶端使用者應在 Lync 用戶端中使用 [**刪除我的登入資訊**] 選項，並從 %localappdata%刪除其 SIP 設定檔資料夾\\Microsoft\\Office\\15.0\\之前先嘗試使用雙因素驗證第一次登入 Lync。

</div>

<div>

## <a name="disablentcredentials"></a>DisableNTCredentials

使用 Kerberos 或 NTLM 驗證方法時，使用者的 Windows 認證可用自動進行驗證。 在一般 Lync Server 2013 部署中其中啟用 Kerberos 及/或 NTLM 驗證，使用者應該不需要輸入他們的認證登入每次。

如果不小心會提示使用者輸入認證提示他們輸入其 pin 碼之前， **DisableNTCredentials**登錄機碼可能會不小心設定用戶端電腦上，可能是透過群組原則。

若要防止其他認證提示，在本機工作站上建立下列登錄項目，或使用 Lync 系統管理範本套用至所有使用者使用 「 群組原則指定集區：

HKEY\_本機\_機器\\軟體\\原則\\Microsoft\\Office\\15.0\\Lync

登錄\_DWORD: DisableNTCredentials

值： 0x0

</div>

<div>

## <a name="savepassword"></a>SavePassword

當使用者登入 Lync 第一次時，會提示使用者儲存他/她的密碼。 如果選取此選項可讓使用者的用戶端憑證] 若要儲存的個人憑證存放區和使用者的 Windows 認證會儲存認證管理員中的本機電腦中。

Lync 設定為支援雙重要素驗證時，應停用**SavePassword**登錄設定。 若要防止使用者儲存其密碼，請變更本機工作站上的下列登錄項目或使用 Lync 系統管理範本套用至所有使用者使用 「 群組原則指定集區：

HKEY\_目前\_使用者\\軟體\\Microsoft\\Office\\15.0\\Lync

登錄\_DWORD: SavePassword

值： 0x0

</div>

</div>

<div>

## <a name="ad-fs-20-token-replay"></a>AD FS 2.0 Token 重新顯示

AD FS 2.0 提供稱為權杖重新執行偵測，依據多個語彙基元的要求使用相同語彙基元可以偵測，然後捨棄的功能。 啟用此功能時，權杖重新執行偵測會用來保護 WS-同盟被動式設定檔和 SAML WebSSO 設定檔中的驗證要求的完整性並確定相同語彙基元永遠不會使用一次以上。

應啟用此功能，在其中安全性是非常高的考量如下的情況下使用 kiosk 時。 權杖重新執行偵測的詳細資訊，請參閱最佳做法，Secure 規劃及部署的 AD FS 2.0 在[https://go.microsoft.com/fwlink/p/?LinkId=309215](https://go.microsoft.com/fwlink/p/?linkid=309215)。

</div>

<div>

## <a name="external-user-access"></a>外部使用者存取

設定 AD FS Proxy 或反向 Proxy，以支援 Lync 雙因素驗證來自外部網路是未深入涵蓋下列主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

