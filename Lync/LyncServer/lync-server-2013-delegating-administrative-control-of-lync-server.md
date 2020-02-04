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

# <a name="delegating-administrative-control-of-lync-server-2013"></a><span data-ttu-id="5a69e-102">委派 Lync Server 2013 管理控制</span><span class="sxs-lookup"><span data-stu-id="5a69e-102">Delegating administrative control of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a69e-103">_**主題上次修改日期：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="5a69e-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="5a69e-104">在 Lync Server 2013 中，系統會使用新的角色存取控制（RBAC）功能，將管理工作委派給使用者。</span><span class="sxs-lookup"><span data-stu-id="5a69e-104">In Lync Server 2013, administrative tasks are delegated to users by using the new role-based access control (RBAC) feature.</span></span> <span data-ttu-id="5a69e-105">當您安裝 Lync Server 時，系統會為您建立許多 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="5a69e-105">When you install Lync Server, a number of RBAC roles are created for you.</span></span> <span data-ttu-id="5a69e-106">這些角色會與 Active Directory 網域服務中的通用安全性群組相對應。</span><span class="sxs-lookup"><span data-stu-id="5a69e-106">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="5a69e-107">例如，RBAC 角色 CsHelpDesk 會對應到 Active Directory 網域服務的 [使用者] 容器中找到的 [CsHelpDesk] 群組。</span><span class="sxs-lookup"><span data-stu-id="5a69e-107">For example, the RBAC role CsHelpDesk corresponds to the CsHelpDesk group found in the Users container in Active Directory Domain Services.</span></span> <span data-ttu-id="5a69e-108">此外，每個 RBAC 角色都與一組 Lync Server Windows PowerShell Cmdlet 相關聯。</span><span class="sxs-lookup"><span data-stu-id="5a69e-108">In addition, each RBAC role is associated with a set of Lync Server Windows PowerShell cmdlets.</span></span> <span data-ttu-id="5a69e-109">這些 Cmdlet 代表指派給指定 RBAC 角色的使用者可執行檔工作。</span><span class="sxs-lookup"><span data-stu-id="5a69e-109">These cmdlets represent the tasks that can be carried out by users who have been assigned the given RBAC role.</span></span> <span data-ttu-id="5a69e-110">例如，已為 CsHelpDesk 角色指派 Lock CsClientPin 和 UnlockCsClientPin Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5a69e-110">For example, the CsHelpDesk role has been assigned the Lock-CsClientPin and UnlockCsClientPin cmdlets.</span></span> <span data-ttu-id="5a69e-111">這表示已獲指派 CsHelpDesk 角色的使用者可以鎖定和解除鎖定使用者 PIN 碼。</span><span class="sxs-lookup"><span data-stu-id="5a69e-111">That means users who have been assigned the CsHelpDesk role can lock and unlock user PIN numbers.</span></span> <span data-ttu-id="5a69e-112">不過，CsHelpDesk 角色尚未獲指派新的-CsVoicePolicy Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5a69e-112">However, the CsHelpDesk role has not been assigned the New-CsVoicePolicy cmdlet.</span></span> <span data-ttu-id="5a69e-113">這表示已獲指派 CsHelpDesk 角色的使用者無法建立新的語音原則。</span><span class="sxs-lookup"><span data-stu-id="5a69e-113">That means that users who have been assigned the CsHelpDesk role cannot create new voice policies.</span></span>

<div>

## <a name="viewing-information-about-rbac-roles"></a><span data-ttu-id="5a69e-114">查看 RBAC 角色的相關資訊</span><span class="sxs-lookup"><span data-stu-id="5a69e-114">Viewing Information about RBAC Roles</span></span>

<span data-ttu-id="5a69e-115">您可以從 Lync Server 管理命令介面中執行下列命令，以取得有關您的 RBAC 角色的基本資訊：</span><span class="sxs-lookup"><span data-stu-id="5a69e-115">You can retrieve basic information about your RBAC roles by running the following command from within the Lync Server Management Shell:</span></span>

    Get-CsAdminRole

<span data-ttu-id="5a69e-116">請記住，RBAC 角色的身分識別（例如，CsVoiceAdministrator）與 Active Directory 網域服務中的 [使用者] 容器中找到的安全性群組是直接對應的。</span><span class="sxs-lookup"><span data-stu-id="5a69e-116">Keep in mind that the Identity of the RBAC role (for example, CsVoiceAdministrator) has a direct mapping to a security group found in the Users container in Active Directory Domain Services.</span></span>

<span data-ttu-id="5a69e-117">若要查看已指派給角色的 Cmdlet 清單，請使用類似以下的命令：</span><span class="sxs-lookup"><span data-stu-id="5a69e-117">To view a list of the cmdlets that have been assigned to a role, use a command similar to this:</span></span>

    Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets

</div>

<div>

## <a name="assigning-an-rbac-role-to-a-user"></a><span data-ttu-id="5a69e-118">指派 RBAC 角色給使用者</span><span class="sxs-lookup"><span data-stu-id="5a69e-118">Assigning an RBAC Role to a User</span></span>

<span data-ttu-id="5a69e-119">若要將 RBAC 角色指派給使用者，您必須將該使用者新增至適當的 Active Directory 安全性群組。</span><span class="sxs-lookup"><span data-stu-id="5a69e-119">To assign an RBAC role to a user, you must add that user to the appropriate Active Directory security group.</span></span> <span data-ttu-id="5a69e-120">例如，若要將 CsLocationAdministrator 角色指派給使用者，您必須將該使用者新增到 [CsLocationAdministrator] 群組。</span><span class="sxs-lookup"><span data-stu-id="5a69e-120">For example, to assign the CsLocationAdministrator role to a user, you must add that user to the CsLocationAdministrator group.</span></span> <span data-ttu-id="5a69e-121">您可以執行下列程式來完成工作：</span><span class="sxs-lookup"><span data-stu-id="5a69e-121">That can be done by carrying out the following procedure:</span></span>

<span data-ttu-id="5a69e-122">**指派使用者至安全性群組**</span><span class="sxs-lookup"><span data-stu-id="5a69e-122">**To assign a user to a security group**</span></span>

1.  <span data-ttu-id="5a69e-123">使用有權修改 Active Directory 群組成員資格的帳戶，登入已安裝 Active Directory 使用者和電腦的電腦。</span><span class="sxs-lookup"><span data-stu-id="5a69e-123">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers has been installed.</span></span>

2.  <span data-ttu-id="5a69e-124">按一下 [**開始**]，按一下 [**所有程式**]，按一下 [系統**管理工具**]，然後按一下 [ **Active Directory 使用者和電腦**]。</span><span class="sxs-lookup"><span data-stu-id="5a69e-124">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>

3.  <span data-ttu-id="5a69e-125">在 [Active Directory 使用者和電腦] 中，展開您網域的名稱，然後按一下 [**使用者**] 容器。</span><span class="sxs-lookup"><span data-stu-id="5a69e-125">In Active Directory Users and Computers, expand the name of your domain and click the **Users** container.</span></span>

4.  <span data-ttu-id="5a69e-126">以滑鼠右鍵按一下安全性群組**CsLocationAdministrator**，然後按一下 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="5a69e-126">Right-click the security group **CsLocationAdministrator**, and then click **Properties**.</span></span>

5.  <span data-ttu-id="5a69e-127">在 [**屬性**] 對話方塊的 [**成員**] 索引標籤上，按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="5a69e-127">In the **Properties** dialog box, on the **Members** tab, click **Add**.</span></span>

6.  <span data-ttu-id="5a69e-128">在 [**選取使用者、電腦、連絡人或群組**] 對話方塊中，在 [**輸入要選取的物件名稱**] 方塊中，輸入要新增到群組的使用者名稱或顯示名稱（例如， **Ken Myer**），然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="5a69e-128">In the **Select Users, Computers, Contacts, or Groups** dialog box, type the user name or display name of the user to be added to the group (for example, **Ken Myer**) in the **Enter the object names to select** box and then click **OK**.</span></span>

7.  <span data-ttu-id="5a69e-129">按一下 [**屬性**] 對話方塊中的 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="5a69e-129">In the **Properties** dialog box, click **OK**.</span></span>

<span data-ttu-id="5a69e-130">若要確認已指派 RBAC 角色，請使用[CsAdminRoleAssignment](https://docs.microsoft.com/powershell/module/skype/Get-CsAdminRoleAssignment) Cmdlet，將 Cmdlet 傳遞給使用者的 SamAccountName （Active Directory 登入名稱）。</span><span class="sxs-lookup"><span data-stu-id="5a69e-130">To verify that the RBAC role has been assigned, use the [Get-CsAdminRoleAssignment](https://docs.microsoft.com/powershell/module/skype/Get-CsAdminRoleAssignment) cmdlet, passing the cmdlet the SamAccountName (Active Directory logon name) of the user.</span></span> <span data-ttu-id="5a69e-131">例如，請在 Lync Server 管理命令介面中執行此命令：</span><span class="sxs-lookup"><span data-stu-id="5a69e-131">For example, run this command from within the Lync Server Management Shell:</span></span>

    Get-CsAdminRoleAssignment  -Identity "kenmyer"

</div>

</div>

<span> </span>

</div>

</div>

</div>

