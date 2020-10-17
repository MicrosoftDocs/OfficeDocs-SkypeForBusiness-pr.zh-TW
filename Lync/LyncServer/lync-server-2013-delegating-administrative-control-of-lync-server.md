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
# <a name="delegating-administrative-control-of-lync-server-2013"></a><span data-ttu-id="351e5-103">委派 Lync Server 2013 的管理控制權</span><span class="sxs-lookup"><span data-stu-id="351e5-103">Delegating administrative control of Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="351e5-104">_**主題上次修改日期：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="351e5-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="351e5-105">在 Lync Server 2013 中，系統會使用以新角色為基礎的存取控制 (RBAC) 功能，將系統管理工作委派給使用者。</span><span class="sxs-lookup"><span data-stu-id="351e5-105">In Lync Server 2013, administrative tasks are delegated to users by using the new role-based access control (RBAC) feature.</span></span> <span data-ttu-id="351e5-106">當您安裝 Lync 伺服器時，會為您建立許多 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="351e5-106">When you install Lync Server, a number of RBAC roles are created for you.</span></span> <span data-ttu-id="351e5-107">這些角色會對應至 Active Directory 網域服務中的通用安全性群組。</span><span class="sxs-lookup"><span data-stu-id="351e5-107">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="351e5-108">例如，RBAC 角色 CsHelpDesk 會對應至 Active Directory 網域服務中使用者容器內找到的 CsHelpDesk 群組。</span><span class="sxs-lookup"><span data-stu-id="351e5-108">For example, the RBAC role CsHelpDesk corresponds to the CsHelpDesk group found in the Users container in Active Directory Domain Services.</span></span> <span data-ttu-id="351e5-109">此外，每個 RBAC 角色會與一組 Lync Server Windows PowerShell Cmdlet 相關聯。</span><span class="sxs-lookup"><span data-stu-id="351e5-109">In addition, each RBAC role is associated with a set of Lync Server Windows PowerShell cmdlets.</span></span> <span data-ttu-id="351e5-110">這些 Cmdlet 代表已獲指派指定 RBAC 角色之使用者可以執行的工作。</span><span class="sxs-lookup"><span data-stu-id="351e5-110">These cmdlets represent the tasks that can be carried out by users who have been assigned the given RBAC role.</span></span> <span data-ttu-id="351e5-111">例如，CsHelpDesk role 已獲指派 Lock-CsClientPin 和 UnlockCsClientPin Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="351e5-111">For example, the CsHelpDesk role has been assigned the Lock-CsClientPin and UnlockCsClientPin cmdlets.</span></span> <span data-ttu-id="351e5-112">這表示已獲指派 CsHelpDesk 角色的使用者可鎖定和解除鎖定使用者 PIN 碼。</span><span class="sxs-lookup"><span data-stu-id="351e5-112">That means users who have been assigned the CsHelpDesk role can lock and unlock user PIN numbers.</span></span> <span data-ttu-id="351e5-113">不過，CsHelpDesk 角色尚未獲指派 New-CsVoicePolicy Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="351e5-113">However, the CsHelpDesk role has not been assigned the New-CsVoicePolicy cmdlet.</span></span> <span data-ttu-id="351e5-114">這表示已獲指派 CsHelpDesk 角色的使用者無法建立新的語音原則。</span><span class="sxs-lookup"><span data-stu-id="351e5-114">That means that users who have been assigned the CsHelpDesk role cannot create new voice policies.</span></span>

<div>

## <a name="viewing-information-about-rbac-roles"></a><span data-ttu-id="351e5-115">查看 RBAC 角色的相關資訊</span><span class="sxs-lookup"><span data-stu-id="351e5-115">Viewing Information about RBAC Roles</span></span>

<span data-ttu-id="351e5-116">您可以從 Lync Server 管理命令介面中執行下列命令，以取得有關 RBAC 角色的基本資訊：</span><span class="sxs-lookup"><span data-stu-id="351e5-116">You can retrieve basic information about your RBAC roles by running the following command from within the Lync Server Management Shell:</span></span>

    Get-CsAdminRole

<span data-ttu-id="351e5-117">請記住，RBAC 角色的身分識別 (例如，CsVoiceAdministrator) 與 Active Directory 網域服務中使用者容器內找到的安全性群組直接對應。</span><span class="sxs-lookup"><span data-stu-id="351e5-117">Keep in mind that the Identity of the RBAC role (for example, CsVoiceAdministrator) has a direct mapping to a security group found in the Users container in Active Directory Domain Services.</span></span>

<span data-ttu-id="351e5-118">若要查看已指派給角色的 Cmdlet 清單，請使用類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="351e5-118">To view a list of the cmdlets that have been assigned to a role, use a command similar to this:</span></span>

    Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets

</div>

<div>

## <a name="assigning-an-rbac-role-to-a-user"></a><span data-ttu-id="351e5-119">指派 RBAC 角色給使用者</span><span class="sxs-lookup"><span data-stu-id="351e5-119">Assigning an RBAC Role to a User</span></span>

<span data-ttu-id="351e5-120">若要將 RBAC 角色指派給使用者，您必須將該使用者新增至適當的 Active Directory 安全性群組。</span><span class="sxs-lookup"><span data-stu-id="351e5-120">To assign an RBAC role to a user, you must add that user to the appropriate Active Directory security group.</span></span> <span data-ttu-id="351e5-121">例如，若要將 CsLocationAdministrator 角色指派給使用者，您必須將該使用者新增至 CsLocationAdministrator 群組。</span><span class="sxs-lookup"><span data-stu-id="351e5-121">For example, to assign the CsLocationAdministrator role to a user, you must add that user to the CsLocationAdministrator group.</span></span> <span data-ttu-id="351e5-122">請執行下列程式來完成：</span><span class="sxs-lookup"><span data-stu-id="351e5-122">That can be done by carrying out the following procedure:</span></span>

<span data-ttu-id="351e5-123">**指派使用者至安全性群組**</span><span class="sxs-lookup"><span data-stu-id="351e5-123">**To assign a user to a security group**</span></span>

1.  <span data-ttu-id="351e5-124">使用有權修改 Active Directory 群組成員資格的帳戶，登入已安裝 Active Directory 使用者和電腦的電腦。</span><span class="sxs-lookup"><span data-stu-id="351e5-124">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers has been installed.</span></span>

2.  <span data-ttu-id="351e5-125">依序按一下 [ **開始**]、[ **所有程式**]、[系統 **管理工具**] 及 [ **Active Directory 使用者及電腦**]。</span><span class="sxs-lookup"><span data-stu-id="351e5-125">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>

3.  <span data-ttu-id="351e5-126">在 [Active Directory 使用者及電腦] 中，展開您的網功能變數名稱稱，然後按一下 [ **使用者** ] 容器。</span><span class="sxs-lookup"><span data-stu-id="351e5-126">In Active Directory Users and Computers, expand the name of your domain and click the **Users** container.</span></span>

4.  <span data-ttu-id="351e5-127">以滑鼠右鍵按一下安全性群組 **CsLocationAdministrator**，然後按一下 [ **屬性**]。</span><span class="sxs-lookup"><span data-stu-id="351e5-127">Right-click the security group **CsLocationAdministrator**, and then click **Properties**.</span></span>

5.  <span data-ttu-id="351e5-128">在 [ **屬性** ] 對話方塊的 [ **成員** ] 索引標籤上，按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="351e5-128">In the **Properties** dialog box, on the **Members** tab, click **Add**.</span></span>

6.  <span data-ttu-id="351e5-129">在 [ **選取使用者、電腦、連絡人或群組** ] 對話方塊中，輸入要新增至群組的使用者名稱或顯示名稱 (例如， **Ken Myer**) 在 [ **輸入物件名稱來選取** ] 方塊中，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="351e5-129">In the **Select Users, Computers, Contacts, or Groups** dialog box, type the user name or display name of the user to be added to the group (for example, **Ken Myer**) in the **Enter the object names to select** box and then click **OK**.</span></span>

7.  <span data-ttu-id="351e5-130">在 [內容]\*\*\*\* 對話方塊中，按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="351e5-130">In the **Properties** dialog box, click **OK**.</span></span>

<span data-ttu-id="351e5-131">若要確認已指派 RBAC 角色，請使用 [Get-CsAdminRoleAssignment](https://docs.microsoft.com/powershell/module/skype/Get-CsAdminRoleAssignment) Cmdlet，將此 Cmdlet 傳遞給使用者 SamAccountName (Active Directory 登入名稱) 。</span><span class="sxs-lookup"><span data-stu-id="351e5-131">To verify that the RBAC role has been assigned, use the [Get-CsAdminRoleAssignment](https://docs.microsoft.com/powershell/module/skype/Get-CsAdminRoleAssignment) cmdlet, passing the cmdlet the SamAccountName (Active Directory logon name) of the user.</span></span> <span data-ttu-id="351e5-132">例如，在 Lync Server 管理命令介面中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="351e5-132">For example, run this command from within the Lync Server Management Shell:</span></span>

    Get-CsAdminRoleAssignment  -Identity "kenmyer"

</div>

</div>

<span> </span>

</div>

</div>

</div>

