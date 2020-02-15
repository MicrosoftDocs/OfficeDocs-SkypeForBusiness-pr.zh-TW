---
title: Lync Server 2013： 委派 Lync Server 系統管理的控制
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
ms.openlocfilehash: 028921122b0198e85e7cc95df97355908f517894
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031307"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delegating-administrative-control-of-lync-server-2013"></a>委派 Lync Server 2013 的系統管理控制

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-22_

Lync Server 2013 中管理工作被委派給使用者使用新的角色型存取控制 (RBAC) 功能。 當您安裝 Lync Server 時，會為您建立 RBAC 角色的數量。 這些角色會對應至 Active Directory 網域服務中的萬用安全性群組。 例如，RBAC 角色 CsHelpDesk 會對應至在 Active Directory 網域服務中的 [使用者] 容器中找到 CsHelpDesk 群組。 此外，每個 RBAC 角色相關聯的 Lync Server Windows PowerShell cmdlet 的一組。 這些 cmdlet 代表可以由已指派特定的 RBAC 角色的使用者執行的工作。 例如，Lock-csclientpin 及 UnlockCsClientPin 指令程式，已被指派 CsHelpDesk 的角色。 這表示已指派 CsHelpDesk 角色的使用者可以鎖定和解除鎖定使用者 PIN 號碼。 不過，CsHelpDesk 角色尚未指派 New-csvoicepolicy cmdlet。 這表示已指派 CsHelpDesk 角色的使用者無法建立新的語音原則。

<div>

## <a name="viewing-information-about-rbac-roles"></a>檢視 RBAC 角色的相關資訊

您可以擷取有關 RBAC 角色的基本資訊執行從 Lync Server 管理命令介面中的下列命令：

    Get-CsAdminRole

請記住，RBAC 角色 (例如，CsVoiceAdministrator) 的身分識別會直接對應至 Active Directory 網域服務中的 [使用者] 容器中找到的安全性群組。

若要檢視已指派給角色的 cmdlet 清單，請使用類似如下的命令：

    Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets

</div>

<div>

## <a name="assigning-an-rbac-role-to-a-user"></a>將 RBAC 角色指派給使用者

RBAC 角色指派給使用者，您必須將該使用者新增至適當的 Active Directory 安全性群組。 例如，您必須將 CsLocationAdministrator 角色指派給使用者，該使用者新增至 [CsLocationAdministrator] 群組。 可以藉由執行下列程序：

**若要將使用者指派給安全性群組**

1.  使用有權修改 Active Directory 群組的成員資格，請登入電腦帳戶已安裝 Active Directory 使用者和電腦。

2.  按一下 [**開始]**、 [**所有程式]**、 [**系統管理工具**]，然後按一下**Active Directory 使用者和電腦**。

3.  Active Directory 使用者及電腦] 中展開 [您的網域名稱，按一下 [**使用者**] 容器。

4.  以滑鼠右鍵按一下 [ **CsLocationAdministrator**中的 [安全性] 群組，然後按一下 [**內容**。

5.  在 [**屬性**] 對話方塊的 [**成員**] 索引標籤中，按一下 [**新增**]。

6.  在 [**選取使用者、 電腦、 連絡人或群組**] 對話方塊中，輸入使用者名稱或中 [**輸入物件名稱來選取**] 方塊中顯示新增至群組 (例如， **Ken Myer**) 的使用者名稱，然後按一下 **[確定]**。

7.  在 [內容]**** 對話方塊中，按一下 [確定]****。

若要確認已指派的 RBAC 角色，請使用[Get-csadminroleassignment](https://docs.microsoft.com/powershell/module/skype/Get-CsAdminRoleAssignment) cmdlet，將 cmdlet 傳遞使用者的 SamAccountName （Active Directory 登入名稱）。 例如，從執行此命令在 Lync Server 管理命令介面：

    Get-CsAdminRoleAssignment  -Identity "kenmyer"

</div>

</div>

<span> </span>

</div>

</div>

</div>

