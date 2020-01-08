---
title: Lync Server 2013：規劃角色型存取控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for role-based access control (RBAC)
ms:assetid: 41204ba3-ce5b-41a8-a6c3-b444468fa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425917(v=OCS.15)
ms:contentKeyID: 48183962
ms.date: 01/28/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1771eb906685294e588e0c67b1fa8fb1f67a8b6e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975040"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-role-based-access-control-in-lync-server-2013"></a>在 Lync Server 2013 中規劃角色型存取控制

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-01-27_

為了讓您能夠委派系統管理工作，同時維持高安全性的標準，Lync Server 2013 提供了角色式存取控制（RBAC）。 使用 RBAC，系統會將使用者指派給管理角色，以獲得系統管理許可權。 Lync Server 2013 包含一組豐富的內建管理角色，也可讓您建立新的角色，並為每個新角色指定自訂的 Cmdlet 清單。 您也可以為預先定義及自訂 RBAC 角色，新增 Cmdlet 指令碼至其允許的工作中。

<div>

## <a name="better-server-security-and-centralization"></a>更好的伺服器安全性與集中化

使用 RBAC、存取和授權是完全根據使用者的 Lync 伺服器角色。 這可讓您使用「最低許可權」的安全性做法，只為管理員和使用者授予其工作所需的權力。

<div>


> [!IMPORTANT]  
> RBAC 限制只適用于使用 Lync Server [控制台] 或 [Lync Server 管理命令介面] 進行遠端作業的管理員。 坐在執行 Lync Server 伺服器的使用者不受 RBAC 限制。 因此，您的 Lync 伺服器的物理安全性對於保留 RBAC 限制是很重要的。



</div>

</div>

<div>

## <a name="roles-and-scope"></a>角色和範圍

在 RBAC 中，*角色*可讓您使用一份 Cmdlet 清單，專門針對特定類型的系統管理員或技術人員提供此功能。 *範圍*是角色中定義的 Cmdlet 可以執行的一組物件。 範圍所影響的物件可以是使用者帳戶（依組織單位分組）或伺服器（依網站分組）。

下表列出 Lync Server 中的預先定義角色，並簡要說明每個作業所能執行的工作類型。 第四欄顯示與每個 Lync 伺服器角色相似的 Microsoft Exchange Server 角色（如果有的話）。

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
<th>基礎 Active Directory 群組</th>
<th>Exchange 對等</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CsAdministrator</p></td>
<td><p>可以執行所有系統管理工作並修改所有設定，包括建立角色並將使用者指派給角色。 可以新增網站、池及服務來展開部署。</p></td>
<td><p>CSAdministrator</p></td>
<td><p>組織管理</p></td>
</tr>
<tr class="even">
<td><p>CsUserAdministrator</p></td>
<td><p>可以啟用和停用 Lync Server 的使用者、移動使用者，以及將現有的原則指派給使用者。 無法修改原則。</p></td>
<td><p>CSUserAdministrator</p></td>
<td><p>郵件收件者</p></td>
</tr>
<tr class="odd">
<td><p>CsVoiceAdministrator</p></td>
<td><p>可以建立、設定及管理語音相關設定與原則。</p></td>
<td><p>CSVoiceAdministrator</p></td>
<td><p>不適用</p></td>
</tr>
<tr class="even">
<td><p>CsServerAdministrator</p></td>
<td><p>可以管理、監控及疑難排解伺服器和服務。 可以避免新的伺服器連線、停止及啟動服務，以及套用軟體更新。 無法對全域設定影響進行變更。</p></td>
<td><p>CSServerAdministrator</p></td>
<td><p>伺服器管理</p></td>
</tr>
<tr class="odd">
<td><p>CsViewOnlyAdministrator</p></td>
<td><p>可以查看部署，包括使用者和伺服器資訊，以便監視部署健康情況。</p></td>
<td><p>CSViewOnlyAdministrator</p></td>
<td><p>僅供查看的組織管理</p></td>
</tr>
<tr class="even">
<td><p>CsHelpDesk</p></td>
<td><p>可以查看部署，包括使用者的屬性和原則。 可以執行特定的疑難排解工作。 無法變更使用者屬性或原則、伺服器設定或服務。</p></td>
<td><p>CSHelpDesk</p></td>
<td><p>技術</p></td>
</tr>
<tr class="odd">
<td><p>CsArchivingAdministrator</p></td>
<td><p>可以修改封存配置和原則。</p></td>
<td><p>CSArchivingAdministrator</p></td>
<td><p>保留管理，法律封存</p></td>
</tr>
<tr class="even">
<td><p>CsResponseGroupAdministrator</p></td>
<td><p>可管理網站內回應群組應用程式的設定。</p></td>
<td><p>CSResponseGroupAdministrator</p></td>
<td><p>不適用</p></td>
</tr>
<tr class="odd">
<td><p>CsLocationAdministrator</p></td>
<td><p>增強型9-1-1 （E9-1-1）管理的最低許可權等級，包括建立 E9-1 個位置和網路識別碼，並將它們相互關聯。 這個角色永遠會指派給全域範圍。</p></td>
<td><p>CSLocationAdministrator</p></td>
<td><p>不適用</p></td>
</tr>
<tr class="even">
<td><p>CsResponseGroupManager</p></td>
<td><p>可以管理特定的回應群組。</p></td>
<td><p>CSResponseGroupManager</p></td>
<td><p>不適用</p></td>
</tr>
<tr class="odd">
<td><p>CsPersistentChatAdministrator</p></td>
<td><p>可以管理持續聊天功能與特定的持續聊天室。</p></td>
<td><p>CSPersistentChatAdministrator</p></td>
<td><p>不適用</p></td>
</tr>
</tbody>
</table>


所有在 Lync Server 隨附的預先定義角色都有全域範圍。 若要遵循最低許可權做法，請不要將使用者指派給擁有全域範圍的角色（如果他們只要管理有限的一組伺服器或使用者）。 若要完成此作業，您可以建立以現有角色為基礎的角色，但範圍較有限。

<div>

## <a name="creating-a-scoped-role"></a>建立作用中角色

當您建立擁有有限範圍（作用中角色）的角色時，您會指定該範圍，以及它所依據的現有角色，以及要指派給該角色的 Active Directory 群組。 您指定的 Active Directory 群組必須已建立。 下列 Cmdlet 是建立具有其中一個預先定義之系統管理角色之許可權但範圍有限的角色的範例。 它會建立名`Site01 Server Administrators`為的新角色。 角色具有預先定義之 CsServerAdministrator 角色的功能，但只適用于位於 Site01 網站的伺服器。 若要使用此 Cmdlet，必須已定義 Site01 網站，且名為`Site01 Server Administrators`的通用安全性群組必須已經存在。

    New-CsAdminRole -Identity "Site01 Server Administrators" -Template CsServerAdministrator -ConfigScopes "site:Site01"

執行此 Cmdlet 之後，所有是`Site01 Server Administrators`群組成員的使用者將擁有 Site01 中伺服器的伺服器系統管理員許可權。 此外，稍後新增到此通用安全性群組的任何使用者也會取得此角色的許可權。 請注意，角色本身以及指派給它的通用安全性群組都會被叫`Site01 Server Administrators`用。

下列範例會限制使用者範圍，而不是伺服器範圍。 它會建立`Sales Users Administrator`一個角色來管理組織單位中的使用者帳戶。 必須先建立 SalesUsersAdministrator 通用安全性群組，才能使用此 Cmdlet。

    New-CsAdminRole -Identity "Sales Users Administrator " -Template CsUserAdministrator -UserScopes "OU:OU=Sales, OU=Lync Tenants, DC=Domain, DC=com"

</div>

<div>

## <a name="creating-a-new-role"></a>建立新的角色

若要建立能夠存取不在其中一個預先定義的角色或一組腳本或模組的一組 Cmdlet 的角色，您也可以使用其中一個預先定義的角色做為範本來開始。 請注意，角色可以執行的腳本和模組必須儲存在下列位置：

  - Lync\\模組路徑，預設為 C： Program files\\常見檔案\\Microsoft Lync Server 2013\\模組 Lync\\

  - 使用者腳本\\路徑，預設為 C： Program files\\常見檔案\\Microsoft Lync Server 2013 AdminScripts\\

若要建立新的角色，您可以使用**CsAdminRole** Cmdlet。 在執行**新的 CsAdminRole**之前，您必須先建立將與此角色相關聯的基礎通用安全性群組。

下列 Cmdlet 是建立新角色的範例。 它們會建立名`MyHelpDeskScriptRole`為的新角色類型。 新角色具有預先定義的 CsHelpDesk 角色的功能，而且還可以在名為 "testscript" 的腳本中執行這些函數。

    New-CsAdminRole -Identity "MyHelpDeskScriptRole" -Template CsHelpDesk -ScriptModules @{Add="testScript.ps1"}

若要使用此 Cmdlet，您必須先建立通用安全性群組 MyHelpDeskScriptRole。

在執行此 Cmdlet 之後，您可以直接將使用者指派給這個角色（在這種情況下，它們擁有全域範圍），或根據這個角色建立作用中的角色，如在此檔中建立作用中的角色中所述。

</div>

<div>

## <a name="assigning-roles-to-users"></a>指派角色給使用者

每個 Lync 伺服器角色都會與基礎 Active Directory 通用安全群組相關聯。 您新增至基礎群組的任何使用者都會取得該角色的功能。

上述各節中的範例都建立了新的角色，並將現有的通用安全性群組指派給新的角色。 若要將現有的角色指派給一或多個使用者，請將這些使用者新增到與該角色相關聯的群組。 您可以將個別使用者和通用安全性群組新增到這些群組中。

例如，系統會自動將**CsAdministrator**角色授與 Active Directory 中的**CS 系統管理員**通用安全性群組。 當您部署 Lync Server 時，會在 Active Directory 中建立這個 [通用安全性群組]。 若要授予使用者或群組此許可權，您只要將其新增至 [ **CS 管理員**] 群組即可。

您可以將多個 RBAC 角色新增到對應到每個角色的基礎 Active Directory 群組，以取得該使用者。

請注意，當您建立角色時，稍後新增至基礎 Active Directory 群組的使用者會獲得該角色的功能。

</div>

<div>

## <a name="modifying-the-abilities-of-a-role"></a>修改角色的功能

您可以修改角色可以執行的 Cmdlet 與腳本清單。 您可以同時修改自訂角色可以執行的 Cmdlet 與腳本，但您只能修改預先定義角色的腳本。 您輸入的每個 Cmdlet 都可以新增、移除或取代 Cmdlet 或腳本。

若要修改角色，請使用**CsAdminRole** Cmdlet。 下列 Cmdlet 會從角色中移除一個腳本。

    Set-CsAdminRole -Identity "MyHelpDeskScriptRole" -ScriptModules @{Remove="testScript.ps1"}

</div>

</div>

<div>

## <a name="planning-for-rbac"></a>RBAC 的規劃

針對您的 Lync Server 部署，要取得任何類型的管理許可權的每個使用者，請考慮他們需要執行的工作，然後將他們指派給其工作所需的最少許可權和範圍。 如有需要，您可以使用**CsAdminRole** Cmdlet 來建立只有此人的工作所需的 Cmdlet 的新角色。

擁有 CsAdministrator 角色的使用者可以建立所有類型的角色，包括以 CsAdministrator 為基礎的角色，並將使用者指派給他們。 最佳做法是將 CsAdministrator 角色指派給一組非常小的信任使用者。

</div>

</div>

<span> </span>

</div>

</div>

</div>

