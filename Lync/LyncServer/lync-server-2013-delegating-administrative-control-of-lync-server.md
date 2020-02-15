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

# <a name="delegating-administrative-control-of-lync-server-2013"></a><span data-ttu-id="a0cea-102">委派 Lync Server 2013 的系統管理控制</span><span class="sxs-lookup"><span data-stu-id="a0cea-102">Delegating administrative control of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0cea-103">_**上次修改主題：** 2013年-02-22_</span><span class="sxs-lookup"><span data-stu-id="a0cea-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="a0cea-104">Lync Server 2013 中管理工作被委派給使用者使用新的角色型存取控制 (RBAC) 功能。</span><span class="sxs-lookup"><span data-stu-id="a0cea-104">In Lync Server 2013, administrative tasks are delegated to users by using the new role-based access control (RBAC) feature.</span></span> <span data-ttu-id="a0cea-105">當您安裝 Lync Server 時，會為您建立 RBAC 角色的數量。</span><span class="sxs-lookup"><span data-stu-id="a0cea-105">When you install Lync Server, a number of RBAC roles are created for you.</span></span> <span data-ttu-id="a0cea-106">這些角色會對應至 Active Directory 網域服務中的萬用安全性群組。</span><span class="sxs-lookup"><span data-stu-id="a0cea-106">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="a0cea-107">例如，RBAC 角色 CsHelpDesk 會對應至在 Active Directory 網域服務中的 [使用者] 容器中找到 CsHelpDesk 群組。</span><span class="sxs-lookup"><span data-stu-id="a0cea-107">For example, the RBAC role CsHelpDesk corresponds to the CsHelpDesk group found in the Users container in Active Directory Domain Services.</span></span> <span data-ttu-id="a0cea-108">此外，每個 RBAC 角色相關聯的 Lync Server Windows PowerShell cmdlet 的一組。</span><span class="sxs-lookup"><span data-stu-id="a0cea-108">In addition, each RBAC role is associated with a set of Lync Server Windows PowerShell cmdlets.</span></span> <span data-ttu-id="a0cea-109">這些 cmdlet 代表可以由已指派特定的 RBAC 角色的使用者執行的工作。</span><span class="sxs-lookup"><span data-stu-id="a0cea-109">These cmdlets represent the tasks that can be carried out by users who have been assigned the given RBAC role.</span></span> <span data-ttu-id="a0cea-110">例如，Lock-csclientpin 及 UnlockCsClientPin 指令程式，已被指派 CsHelpDesk 的角色。</span><span class="sxs-lookup"><span data-stu-id="a0cea-110">For example, the CsHelpDesk role has been assigned the Lock-CsClientPin and UnlockCsClientPin cmdlets.</span></span> <span data-ttu-id="a0cea-111">這表示已指派 CsHelpDesk 角色的使用者可以鎖定和解除鎖定使用者 PIN 號碼。</span><span class="sxs-lookup"><span data-stu-id="a0cea-111">That means users who have been assigned the CsHelpDesk role can lock and unlock user PIN numbers.</span></span> <span data-ttu-id="a0cea-112">不過，CsHelpDesk 角色尚未指派 New-csvoicepolicy cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a0cea-112">However, the CsHelpDesk role has not been assigned the New-CsVoicePolicy cmdlet.</span></span> <span data-ttu-id="a0cea-113">這表示已指派 CsHelpDesk 角色的使用者無法建立新的語音原則。</span><span class="sxs-lookup"><span data-stu-id="a0cea-113">That means that users who have been assigned the CsHelpDesk role cannot create new voice policies.</span></span>

<div>

## <a name="viewing-information-about-rbac-roles"></a><span data-ttu-id="a0cea-114">檢視 RBAC 角色的相關資訊</span><span class="sxs-lookup"><span data-stu-id="a0cea-114">Viewing Information about RBAC Roles</span></span>

<span data-ttu-id="a0cea-115">您可以擷取有關 RBAC 角色的基本資訊執行從 Lync Server 管理命令介面中的下列命令：</span><span class="sxs-lookup"><span data-stu-id="a0cea-115">You can retrieve basic information about your RBAC roles by running the following command from within the Lync Server Management Shell:</span></span>

    Get-CsAdminRole

<span data-ttu-id="a0cea-116">請記住，RBAC 角色 (例如，CsVoiceAdministrator) 的身分識別會直接對應至 Active Directory 網域服務中的 [使用者] 容器中找到的安全性群組。</span><span class="sxs-lookup"><span data-stu-id="a0cea-116">Keep in mind that the Identity of the RBAC role (for example, CsVoiceAdministrator) has a direct mapping to a security group found in the Users container in Active Directory Domain Services.</span></span>

<span data-ttu-id="a0cea-117">若要檢視已指派給角色的 cmdlet 清單，請使用類似如下的命令：</span><span class="sxs-lookup"><span data-stu-id="a0cea-117">To view a list of the cmdlets that have been assigned to a role, use a command similar to this:</span></span>

    Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets

</div>

<div>

## <a name="assigning-an-rbac-role-to-a-user"></a><span data-ttu-id="a0cea-118">將 RBAC 角色指派給使用者</span><span class="sxs-lookup"><span data-stu-id="a0cea-118">Assigning an RBAC Role to a User</span></span>

<span data-ttu-id="a0cea-119">RBAC 角色指派給使用者，您必須將該使用者新增至適當的 Active Directory 安全性群組。</span><span class="sxs-lookup"><span data-stu-id="a0cea-119">To assign an RBAC role to a user, you must add that user to the appropriate Active Directory security group.</span></span> <span data-ttu-id="a0cea-120">例如，您必須將 CsLocationAdministrator 角色指派給使用者，該使用者新增至 [CsLocationAdministrator] 群組。</span><span class="sxs-lookup"><span data-stu-id="a0cea-120">For example, to assign the CsLocationAdministrator role to a user, you must add that user to the CsLocationAdministrator group.</span></span> <span data-ttu-id="a0cea-121">可以藉由執行下列程序：</span><span class="sxs-lookup"><span data-stu-id="a0cea-121">That can be done by carrying out the following procedure:</span></span>

<span data-ttu-id="a0cea-122">**若要將使用者指派給安全性群組**</span><span class="sxs-lookup"><span data-stu-id="a0cea-122">**To assign a user to a security group**</span></span>

1.  <span data-ttu-id="a0cea-123">使用有權修改 Active Directory 群組的成員資格，請登入電腦帳戶已安裝 Active Directory 使用者和電腦。</span><span class="sxs-lookup"><span data-stu-id="a0cea-123">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers has been installed.</span></span>

2.  <span data-ttu-id="a0cea-124">按一下 [**開始]**、 [**所有程式]**、 [**系統管理工具**]，然後按一下**Active Directory 使用者和電腦**。</span><span class="sxs-lookup"><span data-stu-id="a0cea-124">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>

3.  <span data-ttu-id="a0cea-125">Active Directory 使用者及電腦] 中展開 [您的網域名稱，按一下 [**使用者**] 容器。</span><span class="sxs-lookup"><span data-stu-id="a0cea-125">In Active Directory Users and Computers, expand the name of your domain and click the **Users** container.</span></span>

4.  <span data-ttu-id="a0cea-126">以滑鼠右鍵按一下 [ **CsLocationAdministrator**中的 [安全性] 群組，然後按一下 [**內容**。</span><span class="sxs-lookup"><span data-stu-id="a0cea-126">Right-click the security group **CsLocationAdministrator**, and then click **Properties**.</span></span>

5.  <span data-ttu-id="a0cea-127">在 [**屬性**] 對話方塊的 [**成員**] 索引標籤中，按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="a0cea-127">In the **Properties** dialog box, on the **Members** tab, click **Add**.</span></span>

6.  <span data-ttu-id="a0cea-128">在 [**選取使用者、 電腦、 連絡人或群組**] 對話方塊中，輸入使用者名稱或中 [**輸入物件名稱來選取**] 方塊中顯示新增至群組 (例如， **Ken Myer**) 的使用者名稱，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="a0cea-128">In the **Select Users, Computers, Contacts, or Groups** dialog box, type the user name or display name of the user to be added to the group (for example, **Ken Myer**) in the **Enter the object names to select** box and then click **OK**.</span></span>

7.  <span data-ttu-id="a0cea-129">在 [內容]\*\*\*\* 對話方塊中，按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a0cea-129">In the **Properties** dialog box, click **OK**.</span></span>

<span data-ttu-id="a0cea-130">若要確認已指派的 RBAC 角色，請使用[Get-csadminroleassignment](https://docs.microsoft.com/powershell/module/skype/Get-CsAdminRoleAssignment) cmdlet，將 cmdlet 傳遞使用者的 SamAccountName （Active Directory 登入名稱）。</span><span class="sxs-lookup"><span data-stu-id="a0cea-130">To verify that the RBAC role has been assigned, use the [Get-CsAdminRoleAssignment](https://docs.microsoft.com/powershell/module/skype/Get-CsAdminRoleAssignment) cmdlet, passing the cmdlet the SamAccountName (Active Directory logon name) of the user.</span></span> <span data-ttu-id="a0cea-131">例如，從執行此命令在 Lync Server 管理命令介面：</span><span class="sxs-lookup"><span data-stu-id="a0cea-131">For example, run this command from within the Lync Server Management Shell:</span></span>

    Get-CsAdminRoleAssignment  -Identity "kenmyer"

</div>

</div>

<span> </span>

</div>

</div>

</div>

