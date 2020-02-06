---
title: 建立常設聊天室管理員
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5c3892e4-ebae-453e-8107-f42ec0436ea2
description: 摘要：請閱讀本主題，瞭解如何建立持久聊天伺服器系統管理員角色，以便在商務用 Skype Server 2015 中開始設定及管理持續聊天服務。
ms.openlocfilehash: 987183b8ca5cc32e2888040b43d61e5d6fcac09b
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794101"
---
# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a><span data-ttu-id="b7383-103">建立常設聊天室管理員</span><span class="sxs-lookup"><span data-stu-id="b7383-103">Create a Persistent Chat administrator in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b7383-104">**摘要：** 請閱讀本主題，瞭解如何建立持久聊天伺服器系統管理員角色，以便在商務用 Skype Server 2015 中開始設定及管理永久性聊天服務。</span><span class="sxs-lookup"><span data-stu-id="b7383-104">**Summary:** Read this topic to learn how to create a Persistent Chat Server administrator role to enable initial configuration and management of Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="b7383-105">在商務用 Skype Server 中，執行特定工作的使用者必須指派為一或多個特定群組的成員。</span><span class="sxs-lookup"><span data-stu-id="b7383-105">In Skype for Business Server, users who perform specific tasks must be assigned as members of one or more specific groups.</span></span> <span data-ttu-id="b7383-106">角色式存取控制（RBAC）是用來將使用者指派至預先定義的商務用 Skype Server 系統管理角色，以授與許可權。</span><span class="sxs-lookup"><span data-stu-id="b7383-106">Role-Based Access Control (RBAC) is used to grant privileges by assigning users to predefined Skype for Business Server administrative roles.</span></span> <span data-ttu-id="b7383-107">這些角色會與 Active Directory 網域服務中的通用安全性群組相對應。</span><span class="sxs-lookup"><span data-stu-id="b7383-107">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="b7383-108">永久聊天系統管理員安全性群組的成員（CsPersistentChatAdministrator）會獲授與永久聊天伺服器 Cmdlet 的存取權，可以使用商務用 Skype Server 管理命令介面或商務用 Skype 來執行。伺服器 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="b7383-108">Members of the Persistent Chat Administrator security group, CsPersistentChatAdministrator, are granted access to the Persistent Chat Server cmdlets, which can be executed using either the Skype for Business Server Management Shell or the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="b7383-109">在設定及管理持續性聊天伺服器之前，請確定適當的使用者權利和許可權已就緒，且任何將充當永久聊天系統管理員的使用者，都會新增到 [永久聊天管理員] 安全性群組。</span><span class="sxs-lookup"><span data-stu-id="b7383-109">Before configuring and administering Persistent Chat Server, be sure that the appropriate user rights and permissions are in place, and that any users who will act as Persistent Chat administrators are added to the Persistent Chat Administrator security group.</span></span>
  
> [!NOTE] 
> <span data-ttu-id="b7383-110">商務用 Skype Server 2015 提供持續聊天，但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="b7383-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="b7383-111">團隊中提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="b7383-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="b7383-112">如需詳細資訊，請參閱[Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。</span><span class="sxs-lookup"><span data-stu-id="b7383-112">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="b7383-113">如果您需要使用持續聊天，您可以選擇將需要此功能的使用者遷移至小組，或繼續使用商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="b7383-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

## <a name="create-a-persistent-chat-administrator"></a><span data-ttu-id="b7383-114">建立常設聊天室管理員</span><span class="sxs-lookup"><span data-stu-id="b7383-114">Create a Persistent Chat administrator</span></span>

<span data-ttu-id="b7383-115">若要將使用者新增至持續聊天系統管理員安全性群組，請 CsPersistentChatAdministrator，執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="b7383-115">To add a user to the Persistent Chat Administrator security group, CsPersistentChatAdministrator, perform the following steps:</span></span>
  
1. <span data-ttu-id="b7383-116">使用有權修改 Active Directory 群組成員資格的帳戶，登入已安裝 Active Directory 使用者和電腦的電腦。</span><span class="sxs-lookup"><span data-stu-id="b7383-116">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers have been installed.</span></span>
    
2. <span data-ttu-id="b7383-117">按一下 [開始]，按一下 [所有程式]，按一下 [系統管理工具]，然後按一下 [Active Directory 使用者和電腦]。</span><span class="sxs-lookup"><span data-stu-id="b7383-117">Click Start, click All Programs, click Administrative Tools, and then click Active Directory Users and Computers.</span></span>
    
3. <span data-ttu-id="b7383-118">在 [Active Directory 使用者和電腦] 中，展開您網域的名稱，然後按一下 [使用者] 容器。</span><span class="sxs-lookup"><span data-stu-id="b7383-118">In Active Directory Users and Computers, expand the name of your domain and click the Users container.</span></span>
    
4. <span data-ttu-id="b7383-119">以滑鼠右鍵按一下安全性群組 CsPersistentChatAdministrator，然後按一下 [屬性]。</span><span class="sxs-lookup"><span data-stu-id="b7383-119">Right-click the security group CsPersistentChatAdministrator, and then click Properties.</span></span>
    
5. <span data-ttu-id="b7383-120">在 [屬性] 對話方塊的 [成員] 索引標籤上，按一下 [新增]。</span><span class="sxs-lookup"><span data-stu-id="b7383-120">In the Properties dialog box, on the Members tab, click Add.</span></span>
    
6. <span data-ttu-id="b7383-121">在 [選取使用者、電腦、連絡人或群組] 對話方塊中，于 [輸入要選取的物件名稱] 方塊中，輸入要新增到群組的使用者名稱或 [顯示名稱]，然後按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="b7383-121">In the Select Users, Computers, Contact, or Groups dialog box, type the user name or display name of the user to be added to the group in the Enter the object names to select box and then click OK.</span></span>
    
7. <span data-ttu-id="b7383-122">按一下 [屬性] 對話方塊中的 [確定]。</span><span class="sxs-lookup"><span data-stu-id="b7383-122">In the Properties dialog box, click OK.</span></span>
    

