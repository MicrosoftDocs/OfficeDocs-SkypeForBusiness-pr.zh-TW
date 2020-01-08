---
title: Lync Server 2013：規劃雙因素驗證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for two-factor authentication
ms:assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308562(v=OCS.15)
ms:contentKeyID: 54973683
ms.date: 04/06/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 299d2328ee11ffb893974e48b86922123145ed72
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974924"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-two-factor-authentication-in-lync-server-2013"></a>規劃 Lync Server 2013 中的雙因素驗證

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-04-06_

以下是將 Microsoft Lync Server 2013 環境設定為支援雙因素驗證時的部署考慮事項清單。

<div>

## <a name="client-support"></a>用戶端支援

Lync Server 2013 的 Lync 2013 累計更新：7月2013桌面用戶端和所有行動用戶端目前支援雙因素驗證。

</div>

<div>

## <a name="topology-requirements"></a>拓撲需求

我們強烈建議客戶使用專用的 Lync Server 2013 來部署雙因素驗證，包括 Lync Server 2013 的累積更新：年 7 2013 月緣、主管和使用者池。 若要啟用 Lync 使用者的被動式驗證，其他角色和服務必須停用其他驗證方法，包括下列各項：


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
<td><p>System.webserver</p></td>
<td><p>Director</p></td>
<td><p>Kerberos、NTLM 和憑證</p></td>
</tr>
<tr class="even">
<td><p>Web 服務</p></td>
<td><p>System.webserver</p></td>
<td><p>前端</p></td>
<td><p>Kerberos、NTLM 和憑證</p></td>
</tr>
<tr class="odd">
<td><p>Proxy</p></td>
<td><p>EdgeServer</p></td>
<td><p>左邊</p></td>
<td><p>Kerberos 和 NTLM</p></td>
</tr>
<tr class="even">
<td><p>Proxy</p></td>
<td><p>註冊機構</p></td>
<td><p>前端</p></td>
<td><p>Kerberos 和 NTLM</p></td>
</tr>
</tbody>
</table>


除非在服務層級停用這些驗證類型，否則在您的部署中啟用雙因素驗證之後，所有其他版本的 Lync 用戶端都將無法順利登入。

</div>

<div>

## <a name="lync-service-discovery"></a>Lync 服務探索

內部和/或外部用戶端所使用的 DNS 記錄若要探索 Lync 服務，應該將其設定為解析為無法針對雙因素驗證啟用的 Lync 伺服器。 透過這項設定，沒有啟用雙因素驗證的 Lync Pool 使用者不需要輸入 PIN 就能進行驗證，而 Lync Pool 中啟用了雙因素驗證的使用者必須輸入其 PIN 才能驗證.

</div>

<div>

## <a name="exchange-authentication"></a>Exchange 驗證

已針對 Microsoft Exchange 部署雙因素驗證的客戶，可能會發現 Lync 用戶端中的某些功能無法使用。 這是目前的設計，因為 Lync 用戶端不支援依賴 Exchange 整合之功能的雙因素驗證。

</div>

<div>

## <a name="lync-contacts"></a>Lync 連絡人

已設定為利用「整合連絡人存放區」功能的 Lync 使用者，會在使用雙因素驗證登入後，找不到他們的連絡人。

您應該使用**CsUcsRollback** Cmdlet 來移除整合連絡人存放區中的現有使用者連絡人，並將其儲存在 Lync Server 2013，然後才能啟用雙因素驗證。

</div>

<div>

## <a name="skill-search"></a>技能搜尋

已在 Lync 環境中設定「技能搜尋」功能的客戶，會發現啟用 Lync 的雙因素驗證時，這項功能無法運作。 這是因為 Microsoft SharePoint 目前不支援雙因素驗證。

</div>

<div>

## <a name="lync-credentials"></a>Lync 認證

有幾個有關儲存的 Lync 認證的部署考慮，可能會影響設定為使用雙因素驗證的使用者。

<div>

## <a name="deleting-saved-credentials"></a>刪除儲存的認證

桌面用戶端使用者應該使用 Lync 用戶端中的 [**刪除我的登入資訊**] 選項，並從% localappdata%\\\\MICROSOFT Office\\15.0\\Lync 刪除其 SIP 設定檔資料夾，然後再嘗試使用雙因素驗證進行第一次登入。

</div>

<div>

## <a name="disablentcredentials"></a>DisableNTCredentials

使用 Kerberos 或 NTLM 驗證方法時，系統會自動使用使用者的 Windows 認證來進行驗證。 在支援 Kerberos 和/或 NTLM 的典型 Lync Server 2013 部署中，使用者在每次登入時都不應輸入其認證。

如果在提示使用者輸入 PIN 前，系統不小心提示認證，可能是透過群組原則，在用戶端電腦上無意間設定**DisableNTCredentials**登錄機碼。

若要防止額外的認證提示，請在本機工作站上建立下列登錄專案，或使用 Lync 系統管理範本，以使用群組原則將指定之群組的所有使用者套用到其中：

HKEY\_本機\_電腦\\軟體\\原則\\Microsoft\\Office\\15.0\\Lync

REG\_DWORD： DisableNTCredentials

值：0x0

</div>

<div>

## <a name="savepassword"></a>SavePassword

當使用者第一次登入 Lync 時，系統會提示使用者儲存其密碼。 如果選取此選項，此選項可讓使用者的用戶端憑證儲存在個人憑證存放區，並將使用者的 Windows 認證儲存在本機電腦的認證管理員中。

當 Lync 設定為支援雙因素驗證時，必須停用**SavePassword**登錄設定。 若要防止使用者儲存其密碼，請在本機工作站上變更下列登錄專案，或使用 Lync 管理範本，以使用群組原則將指定之群組的所有使用者套用至所有使用者：

HKEY\_目前\_的\\使用者\\軟體\\Microsoft\\Office\\15.0 Lync

REG\_DWORD： SavePassword

值：0x0

</div>

</div>

<div>

## <a name="ad-fs-20-token-replay"></a>AD FS 2.0 權杖重播

AD FS 2.0 提供稱為權杖重播偵測的功能，可讓您檢測到使用相同權杖的多個權杖要求，然後再將它丟棄。 啟用此功能時，權杖重放偵測會在 WS 同盟備用設定檔和 SAML WebSSO 設定檔中保護驗證要求的完整性，只要確認沒有多次使用相同的權杖。

在安全性非常重要的情況下（例如使用網亭時），應啟用此功能。 如需有關權杖重播偵測的詳細資訊，請參閱安全規劃和部署 AD FS 2.0 的最佳[http://go.microsoft.com/fwlink/p/?LinkId=309215](http://go.microsoft.com/fwlink/p/?linkid=309215)做法。

</div>

<div>

## <a name="external-user-access"></a>外部使用者存取

在這些主題中不涉及設定 AD FS Proxy 或反向 Proxy 以支援 Lync 雙因素驗證。

</div>

</div>

<span> </span>

</div>

</div>

</div>

