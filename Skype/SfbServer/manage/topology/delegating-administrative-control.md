---
title: 委派商務用 Skype Server 的系統管理控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: 5c295ed1233cb8a0900828cb1d1c074de1d0f16f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817269"
---
# <a name="delegate-administrative-control-of-skype-for-business-server"></a><span data-ttu-id="50bda-102">委派商務用 Skype Server 的系統管理控制</span><span class="sxs-lookup"><span data-stu-id="50bda-102">Delegate administrative control of Skype for Business Server</span></span> 

<span data-ttu-id="50bda-103">在商務用 Skype Server 中，系統會使用角色式存取控制（RBAC）功能，將管理工作委派給使用者。</span><span class="sxs-lookup"><span data-stu-id="50bda-103">In Skype for Business Server, administrative tasks are delegated to users by using the role-based access control (RBAC) feature.</span></span> <span data-ttu-id="50bda-104">當您安裝商務用 Skype Server 時，系統會為您建立許多 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="50bda-104">When you install Skype for Business Server, a number of RBAC roles are created for you.</span></span> <span data-ttu-id="50bda-105">這些角色會與 Active Directory 網域服務中的通用安全性群組相對應。</span><span class="sxs-lookup"><span data-stu-id="50bda-105">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="50bda-106">例如，RBAC 角色 CsHelpDesk 會對應到 Active Directory 網域服務的 [使用者] 容器中找到的 [CsHelpDesk] 群組。</span><span class="sxs-lookup"><span data-stu-id="50bda-106">For example, the RBAC role CsHelpDesk corresponds to the CsHelpDesk group found in the Users container in Active Directory Domain Services.</span></span> <span data-ttu-id="50bda-107">此外，每個 RBAC 角色都與一組商務用 Skype Server Windows PowerShell Cmdlet 相關聯。</span><span class="sxs-lookup"><span data-stu-id="50bda-107">In addition, each RBAC role is associated with a set of Skype for Business Server  Windows PowerShell cmdlets.</span></span> <span data-ttu-id="50bda-108">這些 Cmdlet 代表指派給指定 RBAC 角色的使用者可執行檔工作。</span><span class="sxs-lookup"><span data-stu-id="50bda-108">These cmdlets represent the tasks that can be carried out by users who have been assigned the given RBAC role.</span></span> <span data-ttu-id="50bda-109">例如，已為 CsHelpDesk 角色指派 Lock CsClientPin 和 UnlockCsClientPin Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="50bda-109">For example, the CsHelpDesk role has been assigned the Lock-CsClientPin and UnlockCsClientPin cmdlets.</span></span> <span data-ttu-id="50bda-110">這表示已獲指派 CsHelpDesk 角色的使用者可以鎖定和解除鎖定使用者 PIN 碼。</span><span class="sxs-lookup"><span data-stu-id="50bda-110">That means users who have been assigned the CsHelpDesk role can lock and unlock user PIN numbers.</span></span> <span data-ttu-id="50bda-111">不過，CsHelpDesk 角色尚未獲指派新的-CsVoicePolicy Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="50bda-111">However, the CsHelpDesk role has not been assigned the New-CsVoicePolicy cmdlet.</span></span> <span data-ttu-id="50bda-112">這表示已獲指派 CsHelpDesk 角色的使用者無法建立新的語音原則。</span><span class="sxs-lookup"><span data-stu-id="50bda-112">That means that users who have been assigned the CsHelpDesk role cannot create new voice policies.</span></span>

## <a name="viewing-information-about-rbac-roles"></a><span data-ttu-id="50bda-113">查看 RBAC 角色的相關資訊</span><span class="sxs-lookup"><span data-stu-id="50bda-113">Viewing information about RBAC roles</span></span>

<span data-ttu-id="50bda-114">您可以從商務用 Skype Server Management Shell 中執行下列命令，以取得有關 RBAC 角色的基本資訊：</span><span class="sxs-lookup"><span data-stu-id="50bda-114">You can retrieve basic information about your RBAC roles by running the following command from within the Skype for Business Server Management Shell:</span></span>

`Get-CsAdminRole`

<span data-ttu-id="50bda-115">請記住，RBAC 角色的身分識別（例如，CsVoiceAdministrator）與 Active Directory 網域服務中的 [使用者] 容器中找到的安全性群組是直接對應的。</span><span class="sxs-lookup"><span data-stu-id="50bda-115">Keep in mind that the Identity of the RBAC role (for example, CsVoiceAdministrator) has a direct mapping to a security group found in the Users container in Active Directory Domain Services.</span></span>

<span data-ttu-id="50bda-116">若要查看已指派給角色的 Cmdlet 清單，請使用類似以下的命令：</span><span class="sxs-lookup"><span data-stu-id="50bda-116">To view a list of the cmdlets that have been assigned to a role, use a command similar to this:</span></span>

`Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets`

## <a name="assigning-an-rbac-role-to-a-user"></a><span data-ttu-id="50bda-117">指派 RBAC 角色給使用者</span><span class="sxs-lookup"><span data-stu-id="50bda-117">Assigning an RBAC role to a user</span></span>

<span data-ttu-id="50bda-118">若要將 RBAC 角色指派給使用者，您必須將該使用者新增至適當的 Active Directory 安全性群組。</span><span class="sxs-lookup"><span data-stu-id="50bda-118">To assign an RBAC role to a user, you must add that user to the appropriate Active Directory security group.</span></span> <span data-ttu-id="50bda-119">例如，若要將 CsLocationAdministrator 角色指派給使用者，您必須將該使用者新增到 [CsLocationAdministrator] 群組。</span><span class="sxs-lookup"><span data-stu-id="50bda-119">For example, to assign the CsLocationAdministrator role to a user, you must add that user to the CsLocationAdministrator group.</span></span> <span data-ttu-id="50bda-120">您可以執行下列程式來完成工作：</span><span class="sxs-lookup"><span data-stu-id="50bda-120">That can be done by carrying out the following procedure:</span></span>

1. <span data-ttu-id="50bda-121">使用有權修改 Active Directory 群組成員資格的帳戶，登入已安裝 Active Directory 使用者和電腦的電腦。</span><span class="sxs-lookup"><span data-stu-id="50bda-121">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers has been installed.</span></span>
2. <span data-ttu-id="50bda-122">按一下 [**開始**]，按一下 [**所有程式**]，按一下 [系統**管理工具**]，然後按一下 [ **Active Directory 使用者和電腦**]。</span><span class="sxs-lookup"><span data-stu-id="50bda-122">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>
3. <span data-ttu-id="50bda-123">在 [Active Directory 使用者和電腦] 中，展開您網域的名稱，然後按一下 [**使用者**] 容器。</span><span class="sxs-lookup"><span data-stu-id="50bda-123">In Active Directory Users and Computers, expand the name of your domain and click the **Users** container.</span></span>
4. <span data-ttu-id="50bda-124">以滑鼠右鍵按一下安全性群組**CsLocationAdministrator**，然後按一下 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="50bda-124">Right-click the security group **CsLocationAdministrator**, and then click **Properties**.</span></span>
5. <span data-ttu-id="50bda-125">在 [**屬性**] 對話方塊的 [**成員**] 索引標籤上，按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="50bda-125">In the **Properties** dialog box, on the **Members** tab, click **Add**.</span></span>
6. <span data-ttu-id="50bda-126">在 [**選取使用者、電腦、連絡人或群組**] 對話方塊中，在 [**輸入要選取的物件名稱**] 方塊中，輸入要新增到群組的使用者名稱或顯示名稱（例如，Ken Myer），然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="50bda-126">In the **Select Users, Computers, Contacts, or Groups** dialog box, type the user name or display name of the user to be added to the group (for example, Ken Myer) in the **Enter the object names to select** box, and then click **OK**.</span></span>
7. <span data-ttu-id="50bda-127">按一下 [**屬性**] 對話方塊中的 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="50bda-127">In the **Properties** dialog box, click **OK**.</span></span>

<span data-ttu-id="50bda-128">若要確認已指派 RBAC 角色，請使用 CsAdminRoleAssignment Cmdlet，將 Cmdlet 傳遞給使用者的 SamAccountName （Active Directory 登入名稱）。</span><span class="sxs-lookup"><span data-stu-id="50bda-128">To verify that the RBAC role has been assigned, use the Get-CsAdminRoleAssignment cmdlet, passing the cmdlet the SamAccountName (Active Directory logon name) of the user.</span></span> <span data-ttu-id="50bda-129">例如，在商務用 Skype Server Management 命令介面中執行此命令：</span><span class="sxs-lookup"><span data-stu-id="50bda-129">For example, run this command from within the Skype for Business Server Management Shell:</span></span>

`Get-CsAdminRoleAssignment  -Identity "kenmyer"`
