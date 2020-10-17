---
title: Lync Server 2013：規劃雙因素驗證
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
ms.openlocfilehash: 1932164cd1236257bbb81d1503b0310c8c55526e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513450"
---
# <a name="planning-for-two-factor-authentication-in-lync-server-2013"></a>在 Lync Server 2013 中規劃雙因素驗證

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-04-06_

以下是設定 Microsoft Lync Server 2013 環境以支援雙因素驗證時的部署考慮清單。

<div>

## <a name="client-support"></a>用戶端支援

Lync Server 2013 的 Lync 2013 累計更新：7月2013桌面用戶端和所有行動用戶端目前都支援雙因素驗證。

</div>

<div>

## <a name="topology-requirements"></a>拓撲需求

客戶強烈建議使用專用的 Lync Server 2013 （含 Lync Server 2013 的累計更新）來部署雙因素驗證：7月 2013 Edge、Director 和使用者集區。 若要對 Lync 使用者啟用被動式驗證，其他角色和服務必須停用其他驗證方法，包括下列專案：


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>配置類型</th>
<th>服務類型</th>
<th>伺服器角色</th>
<th>要停用的驗證類型</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Web 服務</p></td>
<td><p>WebServer</p></td>
<td><p>Director</p></td>
<td><p>Kerberos、NTLM 和憑證</p></td>
</tr>
<tr class="even">
<td><p>Web 服務</p></td>
<td><p>WebServer</p></td>
<td><p>前端</p></td>
<td><p>Kerberos、NTLM 和憑證</p></td>
</tr>
<tr class="odd">
<td><p>代理</p></td>
<td><p>Edgeserver atl-edge</p></td>
<td><p>銳利</p></td>
<td><p>Kerberos 和 NTLM</p></td>
</tr>
<tr class="even">
<td><p>代理</p></td>
<td><p>處長</p></td>
<td><p>前端</p></td>
<td><p>Kerberos 和 NTLM</p></td>
</tr>
</tbody>
</table>


除非在服務層級停用這些驗證類型，否則在您的部署中啟用兩個要素驗證之後，所有其他版本的 Lync 用戶端將無法順利登入。

</div>

<div>

## <a name="lync-service-discovery"></a>Lync 服務探索

內部和/或外部用戶端使用的 DNS 記錄若要探索 Lync 服務，應設定為解析為未啟用雙因素驗證的 Lync server。 在此設定中，未啟用雙因素驗證的 Lync 集區中的使用者不需要輸入 PIN 碼以進行驗證，而啟用兩個要素驗證的 Lync 集區中的使用者則必須輸入其 PIN 碼以進行驗證。

</div>

<div>

## <a name="exchange-authentication"></a>Exchange 驗證

已部署 Microsoft Exchange 的兩個要素驗證的客戶，可能會發現 Lync 用戶端中的某些功能無法使用。 這是目前的設計，因為 Lync 用戶端不支援依存于 Exchange 整合的功能的兩個要素驗證。

</div>

<div>

## <a name="lync-contacts"></a>Lync 連絡人

設定為使用整合連絡人存放區功能的 Lync 使用者，會發現在使用雙因素驗證來登入後，他們的連絡人已不再可用。

您應該使用 **Invoke-CsUcsRollback** 指令程式，從整合連絡人存放區中移除現有的使用者連絡人，並將其儲存在 Lync Server 2013 中，再啟用兩個要素驗證。

</div>

<div>

## <a name="skill-search"></a>技能搜尋

在 Lync 環境中已設定技能搜尋功能的客戶，會發現啟用了雙因素驗證的 Lync 時，此功能無法運作。 這是設計，因為 Microsoft SharePoint 目前不支援雙因素驗證。

</div>

<div>

## <a name="lync-credentials"></a>Lync 認證

有許多與儲存的 Lync 認證相關的部署考慮，可能會影響設定為使用雙因素驗證的使用者。

<div>

## <a name="deleting-saved-credentials"></a>刪除儲存的認證

桌面用戶端使用者應使用 Lync 用戶端中的 [ **刪除我的登入資訊** ] 選項，並從% localappdata% Microsoft Office 15.0 Lync 刪除其 SIP 設定檔資料夾， \\ \\ \\ \\ 然後再嘗試使用雙因素驗證進行第一次簽署。

</div>

<div>

## <a name="disablentcredentials"></a>DisableNTCredentials

使用 Kerberos 或 NTLM 驗證方法時，會自動使用使用者的 Windows 認證進行驗證。 在一般的 Lync Server 2013 部署中啟用 Kerberos 和/或 NTLM 進行驗證時，使用者在每次登入時都不應輸入其認證。

如果在提示使用者輸入 PIN 碼之前，無意提示使用者輸入其 PIN 碼，則可能會在用戶端電腦上無意間設定 **DisableNTCredentials** 登錄機碼（可能是透過「群組原則」）。

若要防止其他提示輸入認證，請在本機工作站上建立下列登錄專案，或使用 Lync 系統管理範本，套用至使用群組原則的指定集區的所有使用者：

HKEY \_ 本機 \_ 電腦 \\ 軟體 \\ 原則 \\ Microsoft \\ Office \\ 15.0 \\ Lync

REG \_ DWORD： DisableNTCredentials

值：0x0

</div>

<div>

## <a name="savepassword"></a>SavePassword

當使用者第一次登入 Lync 時，系統會提示使用者儲存其密碼。 如果選取此選項，則會允許將使用者的用戶端憑證儲存在個人憑證存放區，並將使用者的 Windows 認證儲存在本機電腦的認證管理員中。

當 Lync 設定為支援雙因素驗證時，應停用 **SavePassword** 登錄設定。 若要防止使用者儲存其密碼，請變更本機工作站上的下列登錄專案，或使用 Lync 系統管理範本，將其套用至指定集區的所有使用者使用群組原則：

HKEY \_ 目前的 \_ 使用者 \\ 軟體 \\ Microsoft \\ Office \\ 15.0 \\ Lync

REG \_ DWORD： SavePassword

值：0x0

</div>

</div>

<div>

## <a name="ad-fs-20-token-replay"></a>AD FS 2.0 權杖重新播放

AD FS 2.0 提供的功能稱為「權杖重新顯示偵測」，可以偵測出使用相同權杖的多個權杖要求，然後再將其丟棄。 啟用此功能時，權杖重新顯示偵測會在 WS-Federation 被動式設定檔和 SAML WebSSO 設定檔中保護驗證要求的完整性，請確定永遠不會使用相同的權杖。

在安全性非常重要的情況下，例如使用亭時，應啟用此功能。 如需權杖重新顯示偵測的相關資訊，請參閱安全規劃及部署 AD FS 2.0 的最佳作法 [https://go.microsoft.com/fwlink/p/?LinkId=309215](https://go.microsoft.com/fwlink/p/?linkid=309215) 。

</div>

<div>

## <a name="external-user-access"></a>外部使用者存取

若要將 AD FS Proxy 或反向 Proxy 設定為支援來自外部網路的 Lync 雙因素驗證，這些主題並未涵蓋這些主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

