---
title: Lync Server 2013： 規劃角色型存取控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for role-based access control (RBAC)
ms:assetid: 41204ba3-ce5b-41a8-a6c3-b444468fa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425917(v=OCS.15)
ms:contentKeyID: 48183962
ms.date: 01/28/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb7a359620c7e93565c0d4ef49c813ff0966989c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046626"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-role-based-access-control-in-lync-server-2013"></a>規劃 Lync Server 2013 中角色型存取控制

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015 年 01 月 27 日_

若要可讓您管理工作委派維持高標準的安全性，Lync Server 2013 提供角色型存取控制 (RBAC)。 使用 RBAC，指派使用者給系統管理角色，即可授與系統管理權限。 Lync Server 2013 包含一組豐富的內建管理角色，也可讓您建立新的角色，並指定自訂清單中的每個新角色的 cmdlet。 您也可以將 Cmdlet 的指令碼新增至預先定義與自訂 RBAC 角色之允許的工作中。

<div>

## <a name="better-server-security-and-centralization"></a>更佳的伺服器安全性與集中性

使用 RBAC，存取和授權根據準確使用者的 Lync 伺服器角色。 如此一來便可讓「最低權限」的安全性實務發揮效用，限制系統管理員與使用者擁有執行工作必要的權限。

<div>


> [!IMPORTANT]  
> RBAC 限制只用於系統管理員在遠端工作、 使用 Lync Server Control Panel] 或 [Lync Server 管理命令介面。 RBAC 不會限制使用者坐在執行 Lync Server 的伺服器。 因此，Lync 伺服器的實體安全性是重要保留 RBAC 限制。



</div>

</div>

<div>

## <a name="roles-and-scope"></a>角色與範圍

在 RBAC，*「角色」* 已經過啟用可使用 Cmdlet 的清單，主要是提供特定類型的系統管理員或技術人員使用。*「範圍」* 指的是角色中定義的 Cmdlet 賴以操作的物件集合。範圍影響的物件可能是使用者帳戶 (依組織單位分組) 或伺服器 (依網站分組)。

下表列出在 Lync Server 中預先定義的角色，並提供之每個可以執行的工作類型的一般概觀。 如果有的話，第四欄會顯示每個 Lync 伺服器角色，類似 Microsoft Exchange Server 角色。

### <a name="predefined-administrative-roles"></a>預先定義的系統管理角色

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>角色</th>
<th>允許的工作</th>
<th>Active Directory 基礎群組</th>
<th>Exchange 相等項目</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CsAdministrator</p></td>
<td><p>可執行所有系統管理工作並修改所有設定，包括建立角色及指派使用者給角色。可新增新的網站、集區與服務，藉以擴充部署項目。</p></td>
<td><p>CSAdministrator</p></td>
<td><p>組織管理</p></td>
</tr>
<tr class="even">
<td><p>CsUserAdministrator</p></td>
<td><p>可以啟用及停用使用者的 Lync Server]，將使用者移並將現有的原則指派給使用者。 無法修改原則。</p></td>
<td><p>CSUserAdministrator</p></td>
<td><p>郵件收件者</p></td>
</tr>
<tr class="odd">
<td><p>CsVoiceAdministrator</p></td>
<td><p>可建立、設定及管理語音相關的設定及原則。</p></td>
<td><p>CSVoiceAdministrator</p></td>
<td><p>不適用</p></td>
</tr>
<tr class="even">
<td><p>CsServerAdministrator</p></td>
<td><p>可對伺服器與相關服務進行管理、監控及疑難排解。可防止對伺服器進行全新的連線作業、停止與啟動服務，以及套用軟體更新。無法進行具有全域組態影響的變更。</p></td>
<td><p>CSServerAdministrator</p></td>
<td><p>伺服器管理</p></td>
</tr>
<tr class="odd">
<td><p>CsViewOnlyAdministrator</p></td>
<td><p>可檢視部署情況 (包括使用者與伺服器資訊) 以監控部署運作情況。</p></td>
<td><p>CSViewOnlyAdministrator</p></td>
<td><p>僅供檢視的組織管理</p></td>
</tr>
<tr class="even">
<td><p>CsHelpDesk</p></td>
<td><p>可檢視部署內容，包括使用者內容與原則。可執行特定疑難排解工作。無法變更使用者內容或原則、伺服器組態或相關服務。</p></td>
<td><p>CSHelpDesk</p></td>
<td><p>服務台</p></td>
</tr>
<tr class="odd">
<td><p>CsArchivingAdministrator</p></td>
<td><p>可修改封存組態與原則。</p></td>
<td><p>CSArchivingAdministrator</p></td>
<td><p>保留管理、法務保存措施</p></td>
</tr>
<tr class="even">
<td><p>CsResponseGroupAdministrator</p></td>
<td><p>可管理網站內的回應群組應用程式組態。</p></td>
<td><p>CSResponseGroupAdministrator</p></td>
<td><p>不適用</p></td>
</tr>
<tr class="odd">
<td><p>CsLocationAdministrator</p></td>
<td><p>最低層級的增強型 9-1-1 (E9-1-1) 管理權限，包括建立 E9-1-1 位置與網路識別碼，並將這些識別碼彼此關聯。此角色一律指派全域範圍。</p></td>
<td><p>CSLocationAdministrator</p></td>
<td><p>不適用</p></td>
</tr>
<tr class="even">
<td><p>CsResponseGroupManager</p></td>
<td><p>可管理特定回應群組。</p></td>
<td><p>CSResponseGroupManager</p></td>
<td><p>不適用</p></td>
</tr>
<tr class="odd">
<td><p>CsPersistentChatAdministrator</p></td>
<td><p>可管理常設聊天功能和特定的常設聊天室。</p></td>
<td><p>CSPersistentChatAdministrator</p></td>
<td><p>不適用</p></td>
</tr>
</tbody>
</table>


所有預先定義的角色是在 Lync Server 具有全域範圍。 為了遵循最低權限實務，當使用者只需要管理有限的伺服器或使用者時，請勿將全域範圍的角色指派給他們。 要達到這個目的，請依據現有的角色建立相關角色，但在範圍上稍做限制即可。

<div>

## <a name="creating-a-scoped-role"></a>建立有範圍的角色

建立範圍有限的角色 (有範圍的角色) 時，您必須指定範圍及其所依據的現有角色，以及要指派該角色的 Active Directory 群組。 您指定的 Active Directory 群組必須事先建立好。 以下 Cmdlet 將示範如何建立範圍有限的角色 (該角色擁有其中一個預先定義管理角色的權限，但範圍有限)。 它會建立新的角色，稱為 「 `Site01 Server Administrators`。 此角色具有預先定義的 CsServerAdministrator 角色功能，但僅適用位於 Site01 網站的伺服器。 若要使用此 cmdlet，必須已經定義 Site01 站台，和萬用資訊安全群組命名為`Site01 Server Administrators`，必須已經存在。

    New-CsAdminRole -Identity "Site01 Server Administrators" -Template CsServerAdministrator -ConfigScopes "site:Site01"

執行此指令程式，身為成員的所有使用者之後的`Site01 Server Administrators`群組將 Site01 中有之伺服器的伺服器系統管理員權限。 此外，任何稍後新增至此萬用資訊安全群組的使用者也會獲得此角色的權限。 請注意，稱為 「 角色本身，以及萬用安全性群組將它指派給`Site01 Server Administrators`。

以下範例將限制使用者範圍，而非伺服器範圍。 它會建立`Sales Users Administrator`若要管理的 Sales 組織單位中的使用者帳戶的角色。 若要使用此 cmdlet 時，必須已建立 SalesUsersAdministrator 萬用安全性群組。

    New-CsAdminRole -Identity "Sales Users Administrator " -Template CsUserAdministrator -UserScopes "OU:OU=Sales, OU=Lync Tenants, DC=Domain, DC=com"

</div>

<div>

## <a name="creating-a-new-role"></a>建立新角色

若要建立一個新角色能夠存取非預先定義角色中的一組 Cmdlet、指令碼或模組，您可再次從使用其中一個預先定義角色為範本開始。請注意，角色可執行的指令碼和模組必須儲存於下列位置：

  - Lync 模組路徑，也就是預設 c:\\Program Files\\通用檔案\\Microsoft Lync Server 2013\\模組\\Lync

  - 使用者指令碼路徑，也就是預設 c:\\Program Files\\通用檔案\\Microsoft Lync Server 2013\\AdminScripts

若要建立新角色，需使用 **New-CsAdminRole** Cmdlet。 在執行之前**新增 Get-csadminrole**，您必須先建立要與此角色建立關聯底層萬用資訊安全群組。

下列 Cmdlet 可作為建立新角色的範例。 他們建立新的角色類型，呼叫`MyHelpDeskScriptRole`。 新角色具有預先定義 CsHelpDesk 角色的功能，可在名為“testscript”的指令碼中額外執行各項功能。

    New-CsAdminRole -Identity "MyHelpDeskScriptRole" -Template CsHelpDesk -ScriptModules @{Add="testScript.ps1"}

若要使用此 cmdlet，您必須先建立通用安全性群組 MyHelpDeskScriptRole。

此 Cmdlet 執行後，就能將使用者直接指派給此角色 (此時使用者擁有全域範圍)，或是依據此角色建立有範圍的角色，如本文件先前在〈建立有範圍的角色〉中所述。

</div>

<div>

## <a name="assigning-roles-to-users"></a>指派角色給使用者

每個 Lync 伺服器角色為基礎的 Active Directory 萬用資訊安全群組相關聯。 您新增至基礎群組的任何使用者都可獲得該角色的功能。

在上述章節中的範例建立新的角色和現有萬用資訊安全群組指派給新角色。 若要將現有角色指派給一或多位使用者，請將這些使用者新增至與該角色關聯的群組。 您可以將個別使用者和萬用資訊安全群組新增至這些群組。

例如， **CsAdministrator**角色會自動授與至 Active Directory 中的 [ **CS 系統管理員**通用的安全性] 群組中。 部署 Lync Server 時，此萬用資訊安全群組會建立在 Active Directory 中。 若要授予使用者或群組這個權限，您只需將其新增至 **CS 系統管理員**群組。

您可以將使用者新增至對應每個群組的 Active Directory 基礎群組，藉此賦予其多重 RBAC 角色。

請注意，當您建立角色時，後續新增至該 Active Directory 基礎群組的使用者將會繼承該角色的權限。

</div>

<div>

## <a name="modifying-the-abilities-of-a-role"></a>修改角色功能

您可以修改角色可執行的 Cmdlet 和指令碼清單；也可同時修改自訂角色可執行的 Cmdlet 和指令碼，但僅能修改預先定義角色的指令碼。每個鍵入的 Cmdlet 均可新增、移除或更換 Cmdlet 或指令碼。

若要修改角色，請使用 **Set-CsAdminRole** Cmdlet。 下列指令程式從角色中移除一個指令碼。

    Set-CsAdminRole -Identity "MyHelpDeskScriptRole" -ScriptModules @{Remove="testScript.ps1"}

</div>

</div>

<div>

## <a name="planning-for-rbac"></a>規劃 RBAC

是要指定任何種類的系統管理權限給 Lync Server 部署每個人，請考慮完全執行，所需的工作，然後將它們指派給擁有最低的權限與他們的工作所需的範圍的角色。 必要時可以使用 **Set-CsAdminRole** Cmdlet 建立只擁有其任務所需 Cmdlet 的新角色。

具有 CsAdministrator 角色的使用者可以建立所有種類的角色，包括依據 CsAdministrator 建立的角色，並將其指派給使用者。最佳做法是將 CsAdministrator 角色指派給非常少數的受信任使用者。

</div>

</div>

<span> </span>

</div>

</div>

</div>

