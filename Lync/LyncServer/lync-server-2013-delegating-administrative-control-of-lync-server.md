---
title: Lync Server 2013：委派 Lync Server 管理控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegating administrative control of Lync Server 2013
ms:assetid: 0f378eff-8ef4-4c60-9fd2-67d7ee259ef8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520951(v=OCS.15)
ms:contentKeyID: 48183418
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 134d5a4abae1173cc1d74cecb876951cea6d72c1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739813"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delegating-administrative-control-of-lync-server-2013"></a>委派 Lync Server 2013 管理控制

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-22_

在 Lync Server 2013 中，系統會使用新的角色存取控制（RBAC）功能，將管理工作委派給使用者。 當您安裝 Lync Server 時，系統會為您建立許多 RBAC 角色。 這些角色會與 Active Directory 網域服務中的通用安全性群組相對應。 例如，RBAC 角色 CsHelpDesk 會對應到 Active Directory 網域服務的 [使用者] 容器中找到的 [CsHelpDesk] 群組。 此外，每個 RBAC 角色都與一組 Lync Server Windows PowerShell Cmdlet 相關聯。 這些 Cmdlet 代表指派給指定 RBAC 角色的使用者可執行檔工作。 例如，已為 CsHelpDesk 角色指派 Lock CsClientPin 和 UnlockCsClientPin Cmdlet。 這表示已獲指派 CsHelpDesk 角色的使用者可以鎖定和解除鎖定使用者 PIN 碼。 不過，CsHelpDesk 角色尚未獲指派新的-CsVoicePolicy Cmdlet。 這表示已獲指派 CsHelpDesk 角色的使用者無法建立新的語音原則。

<div>

## <a name="viewing-information-about-rbac-roles"></a>查看 RBAC 角色的相關資訊

您可以從 Lync Server 管理命令介面中執行下列命令，以取得有關您的 RBAC 角色的基本資訊：

    Get-CsAdminRole

請記住，RBAC 角色的身分識別（例如，CsVoiceAdministrator）與 Active Directory 網域服務中的 [使用者] 容器中找到的安全性群組是直接對應的。

若要查看已指派給角色的 Cmdlet 清單，請使用類似以下的命令：

    Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets

</div>

<div>

## <a name="assigning-an-rbac-role-to-a-user"></a>指派 RBAC 角色給使用者

若要將 RBAC 角色指派給使用者，您必須將該使用者新增至適當的 Active Directory 安全性群組。 例如，若要將 CsLocationAdministrator 角色指派給使用者，您必須將該使用者新增到 [CsLocationAdministrator] 群組。 您可以執行下列程式來完成工作：

**指派使用者至安全性群組**

1.  使用有權修改 Active Directory 群組成員資格的帳戶，登入已安裝 Active Directory 使用者和電腦的電腦。

2.  按一下 [**開始**]，按一下 [**所有程式**]，按一下 [系統**管理工具**]，然後按一下 [ **Active Directory 使用者和電腦**]。

3.  在 [Active Directory 使用者和電腦] 中，展開您網域的名稱，然後按一下 [**使用者**] 容器。

4.  以滑鼠右鍵按一下安全性群組**CsLocationAdministrator**，然後按一下 [**屬性**]。

5.  在 [**屬性**] 對話方塊的 [**成員**] 索引標籤上，按一下 [**新增**]。

6.  在 [**選取使用者、電腦、連絡人或群組**] 對話方塊中，在 [**輸入要選取的物件名稱**] 方塊中，輸入要新增到群組的使用者名稱或顯示名稱（例如， **Ken Myer**），然後按一下 **[確定]**。

7.  按一下 [**屬性**] 對話方塊中的 **[確定]**。

若要確認已指派 RBAC 角色，請使用[CsAdminRoleAssignment](https://docs.microsoft.com/powershell/module/skype/Get-CsAdminRoleAssignment) Cmdlet，將 Cmdlet 傳遞給使用者的 SamAccountName （Active Directory 登入名稱）。 例如，請在 Lync Server 管理命令介面中執行此命令：

    Get-CsAdminRoleAssignment  -Identity "kenmyer"

</div>

</div>

<span> </span>

</div>

</div>

</div>

