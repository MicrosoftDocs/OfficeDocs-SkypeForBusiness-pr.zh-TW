---
title: 委派商務用 Skype Server 的管理控制權
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: eb78fc7e0f831bae1c5dd6e207791e27aa4c68d1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832793"
---
# <a name="delegate-administrative-control-of-skype-for-business-server"></a><span data-ttu-id="430d8-102">委派商務用 Skype Server 的管理控制權</span><span class="sxs-lookup"><span data-stu-id="430d8-102">Delegate administrative control of Skype for Business Server</span></span> 

<span data-ttu-id="430d8-103">在商務用 Skype Server 中，系統會使用以角色為基礎的存取控制 (RBAC) 功能，將系統管理工作委派給使用者。</span><span class="sxs-lookup"><span data-stu-id="430d8-103">In Skype for Business Server, administrative tasks are delegated to users by using the role-based access control (RBAC) feature.</span></span> <span data-ttu-id="430d8-104">當您安裝商務用 Skype Server 時，會為您建立許多 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="430d8-104">When you install Skype for Business Server, a number of RBAC roles are created for you.</span></span> <span data-ttu-id="430d8-105">這些角色會對應至 Active Directory 網域服務中的通用安全性群組。</span><span class="sxs-lookup"><span data-stu-id="430d8-105">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="430d8-106">例如，RBAC 角色 CsHelpDesk 會對應至 Active Directory 網域服務中使用者容器內找到的 CsHelpDesk 群組。</span><span class="sxs-lookup"><span data-stu-id="430d8-106">For example, the RBAC role CsHelpDesk corresponds to the CsHelpDesk group found in the Users container in Active Directory Domain Services.</span></span> <span data-ttu-id="430d8-107">此外，每個 RBAC 角色會與一組商務用 Skype Server Windows PowerShell Cmdlet 相關聯。</span><span class="sxs-lookup"><span data-stu-id="430d8-107">In addition, each RBAC role is associated with a set of Skype for Business Server  Windows PowerShell cmdlets.</span></span> <span data-ttu-id="430d8-108">這些 Cmdlet 代表已獲指派指定 RBAC 角色之使用者可以執行的工作。</span><span class="sxs-lookup"><span data-stu-id="430d8-108">These cmdlets represent the tasks that can be carried out by users who have been assigned the given RBAC role.</span></span> <span data-ttu-id="430d8-109">例如，CsHelpDesk role 已獲指派 Lock-CsClientPin 和 UnlockCsClientPin Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="430d8-109">For example, the CsHelpDesk role has been assigned the Lock-CsClientPin and UnlockCsClientPin cmdlets.</span></span> <span data-ttu-id="430d8-110">這表示已獲指派 CsHelpDesk 角色的使用者可鎖定和解除鎖定使用者 PIN 碼。</span><span class="sxs-lookup"><span data-stu-id="430d8-110">That means users who have been assigned the CsHelpDesk role can lock and unlock user PIN numbers.</span></span> <span data-ttu-id="430d8-111">不過，CsHelpDesk 角色尚未獲指派 New-CsVoicePolicy Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="430d8-111">However, the CsHelpDesk role has not been assigned the New-CsVoicePolicy cmdlet.</span></span> <span data-ttu-id="430d8-112">這表示已獲指派 CsHelpDesk 角色的使用者無法建立新的語音原則。</span><span class="sxs-lookup"><span data-stu-id="430d8-112">That means that users who have been assigned the CsHelpDesk role cannot create new voice policies.</span></span>

## <a name="viewing-information-about-rbac-roles"></a><span data-ttu-id="430d8-113">查看 RBAC 角色的相關資訊</span><span class="sxs-lookup"><span data-stu-id="430d8-113">Viewing information about RBAC roles</span></span>

<span data-ttu-id="430d8-114">您可以從商務用 Skype Server 管理命令介面中執行下列命令，以取得有關 RBAC 角色的基本資訊：</span><span class="sxs-lookup"><span data-stu-id="430d8-114">You can retrieve basic information about your RBAC roles by running the following command from within the Skype for Business Server Management Shell:</span></span>

`Get-CsAdminRole`

<span data-ttu-id="430d8-115">請記住，RBAC 角色的身分識別 (例如，CsVoiceAdministrator) 與 Active Directory 網域服務中使用者容器內找到的安全性群組直接對應。</span><span class="sxs-lookup"><span data-stu-id="430d8-115">Keep in mind that the Identity of the RBAC role (for example, CsVoiceAdministrator) has a direct mapping to a security group found in the Users container in Active Directory Domain Services.</span></span>

<span data-ttu-id="430d8-116">若要查看已指派給角色的 Cmdlet 清單，請使用類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="430d8-116">To view a list of the cmdlets that have been assigned to a role, use a command similar to this:</span></span>

`Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets`

## <a name="assigning-an-rbac-role-to-a-user"></a><span data-ttu-id="430d8-117">指派 RBAC 角色給使用者</span><span class="sxs-lookup"><span data-stu-id="430d8-117">Assigning an RBAC role to a user</span></span>

<span data-ttu-id="430d8-118">若要將 RBAC 角色指派給使用者，您必須將該使用者新增至適當的 Active Directory 安全性群組。</span><span class="sxs-lookup"><span data-stu-id="430d8-118">To assign an RBAC role to a user, you must add that user to the appropriate Active Directory security group.</span></span> <span data-ttu-id="430d8-119">例如，若要將 CsLocationAdministrator 角色指派給使用者，您必須將該使用者新增至 CsLocationAdministrator 群組。</span><span class="sxs-lookup"><span data-stu-id="430d8-119">For example, to assign the CsLocationAdministrator role to a user, you must add that user to the CsLocationAdministrator group.</span></span> <span data-ttu-id="430d8-120">請執行下列程式來完成：</span><span class="sxs-lookup"><span data-stu-id="430d8-120">That can be done by carrying out the following procedure:</span></span>

1. <span data-ttu-id="430d8-121">使用有權修改 Active Directory 群組成員資格的帳戶，登入已安裝 Active Directory 使用者和電腦的電腦。</span><span class="sxs-lookup"><span data-stu-id="430d8-121">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers has been installed.</span></span>
2. <span data-ttu-id="430d8-122">依序按一下 [ **開始**]、[ **所有程式**]、[系統 **管理工具**] 及 [ **Active Directory 使用者及電腦**]。</span><span class="sxs-lookup"><span data-stu-id="430d8-122">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>
3. <span data-ttu-id="430d8-123">在 [Active Directory 使用者及電腦] 中，展開您的網功能變數名稱稱，然後按一下 [ **使用者** ] 容器。</span><span class="sxs-lookup"><span data-stu-id="430d8-123">In Active Directory Users and Computers, expand the name of your domain and click the **Users** container.</span></span>
4. <span data-ttu-id="430d8-124">以滑鼠右鍵按一下安全性群組 **CsLocationAdministrator**，然後按一下 [ **屬性**]。</span><span class="sxs-lookup"><span data-stu-id="430d8-124">Right-click the security group **CsLocationAdministrator**, and then click **Properties**.</span></span>
5. <span data-ttu-id="430d8-125">在 [ **屬性** ] 對話方塊的 [ **成員** ] 索引標籤上，按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="430d8-125">In the **Properties** dialog box, on the **Members** tab, click **Add**.</span></span>
6. <span data-ttu-id="430d8-126">在 [ **選取使用者、電腦、連絡人或群組** ] 對話方塊中，輸入要新增至群組的使用者名稱或顯示名稱 (例如，Ken Myer) 在 [ **輸入物件名稱來選取** ] 方塊中，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="430d8-126">In the **Select Users, Computers, Contacts, or Groups** dialog box, type the user name or display name of the user to be added to the group (for example, Ken Myer) in the **Enter the object names to select** box, and then click **OK**.</span></span>
7. <span data-ttu-id="430d8-127">在 [內容] 對話方塊中，按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="430d8-127">In the **Properties** dialog box, click **OK**.</span></span>

<span data-ttu-id="430d8-128">若要確認已指派 RBAC 角色，請使用 Get-CsAdminRoleAssignment Cmdlet，將此 Cmdlet 傳遞給使用者 SamAccountName (Active Directory 登入名稱) 。</span><span class="sxs-lookup"><span data-stu-id="430d8-128">To verify that the RBAC role has been assigned, use the Get-CsAdminRoleAssignment cmdlet, passing the cmdlet the SamAccountName (Active Directory logon name) of the user.</span></span> <span data-ttu-id="430d8-129">例如，在商務用 Skype Server 管理命令介面中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="430d8-129">For example, run this command from within the Skype for Business Server Management Shell:</span></span>

`Get-CsAdminRoleAssignment  -Identity "kenmyer"`
