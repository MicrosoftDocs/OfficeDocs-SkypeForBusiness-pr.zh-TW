---
title: Lync Server 2013：委派 Lync Server 的管理控制權
description: Lync Server 2013：委派 Lync Server 的管理控制權。
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
ms.openlocfilehash: a8d3710af2d194a5aa4ebdd7291be2ee58176507
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567489"
---
# <a name="delegating-administrative-control-of-lync-server-2013"></a>委派 Lync Server 2013 的管理控制權

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-22_

在 Lync Server 2013 中，系統會使用以新角色為基礎的存取控制 (RBAC) 功能，將系統管理工作委派給使用者。 當您安裝 Lync 伺服器時，會為您建立許多 RBAC 角色。 這些角色會對應至 Active Directory 網域服務中的通用安全性群組。 例如，RBAC 角色 CsHelpDesk 會對應至 Active Directory 網域服務中使用者容器內找到的 CsHelpDesk 群組。 此外，每個 RBAC 角色會與一組 Lync Server Windows PowerShell Cmdlet 相關聯。 這些 Cmdlet 代表已獲指派指定 RBAC 角色之使用者可以執行的工作。 例如，CsHelpDesk role 已獲指派 Lock-CsClientPin 和 UnlockCsClientPin Cmdlet。 這表示已獲指派 CsHelpDesk 角色的使用者可鎖定和解除鎖定使用者 PIN 碼。 不過，CsHelpDesk 角色尚未獲指派 New-CsVoicePolicy Cmdlet。 這表示已獲指派 CsHelpDesk 角色的使用者無法建立新的語音原則。

<div>

## <a name="viewing-information-about-rbac-roles"></a>查看 RBAC 角色的相關資訊

您可以從 Lync Server 管理命令介面中執行下列命令，以取得有關 RBAC 角色的基本資訊：

    Get-CsAdminRole

請記住，RBAC 角色的身分識別 (例如，CsVoiceAdministrator) 與 Active Directory 網域服務中使用者容器內找到的安全性群組直接對應。

若要查看已指派給角色的 Cmdlet 清單，請使用類似下列的命令：

    Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets

</div>

<div>

## <a name="assigning-an-rbac-role-to-a-user"></a>指派 RBAC 角色給使用者

若要將 RBAC 角色指派給使用者，您必須將該使用者新增至適當的 Active Directory 安全性群組。 例如，若要將 CsLocationAdministrator 角色指派給使用者，您必須將該使用者新增至 CsLocationAdministrator 群組。 請執行下列程式來完成：

**指派使用者至安全性群組**

1.  使用有權修改 Active Directory 群組成員資格的帳戶，登入已安裝 Active Directory 使用者和電腦的電腦。

2.  依序按一下 [ **開始**]、[ **所有程式**]、[系統 **管理工具**] 及 [ **Active Directory 使用者及電腦**]。

3.  在 [Active Directory 使用者及電腦] 中，展開您的網功能變數名稱稱，然後按一下 [ **使用者** ] 容器。

4.  以滑鼠右鍵按一下安全性群組 **CsLocationAdministrator**，然後按一下 [ **屬性**]。

5.  在 [ **屬性** ] 對話方塊的 [ **成員** ] 索引標籤上，按一下 [ **新增**]。

6.  在 [ **選取使用者、電腦、連絡人或群組** ] 對話方塊中，輸入要新增至群組的使用者名稱或顯示名稱 (例如， **Ken Myer**) 在 [ **輸入物件名稱來選取** ] 方塊中，然後按一下 **[確定]**。

7.  在 [內容]**** 對話方塊中，按一下 [確定]****。

若要確認已指派 RBAC 角色，請使用 [Get-CsAdminRoleAssignment](https://docs.microsoft.com/powershell/module/skype/Get-CsAdminRoleAssignment) Cmdlet，將此 Cmdlet 傳遞給使用者 SamAccountName (Active Directory 登入名稱) 。 例如，在 Lync Server 管理命令介面中執行下列命令：

    Get-CsAdminRoleAssignment  -Identity "kenmyer"

</div>

</div>

<span> </span>

</div>

</div>

</div>

