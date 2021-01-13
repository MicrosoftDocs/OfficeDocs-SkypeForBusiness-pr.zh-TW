---
title: 在商務用 Skype Server 2015 中建立持續性聊天系統管理員
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5c3892e4-ebae-453e-8107-f42ec0436ea2
description: 摘要：閱讀此主題以瞭解如何建立 Persistent Chat Server 系統管理員角色，以在商務用 Skype Server 2015 中啟用 Persistent 聊天服務的初始設定和管理。
ms.openlocfilehash: eea989b0284353e193ebf99a0be99b2d0811e532
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802093"
---
# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a><span data-ttu-id="e62f6-103">在商務用 Skype Server 2015 中建立持續性聊天系統管理員</span><span class="sxs-lookup"><span data-stu-id="e62f6-103">Create a Persistent Chat administrator in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e62f6-104">**摘要：** 閱讀此主題以瞭解如何建立 Persistent Chat Server 系統管理員角色，以在商務用 Skype Server 2015 中啟用 Persistent Chat service 的初始設定和管理。</span><span class="sxs-lookup"><span data-stu-id="e62f6-104">**Summary:** Read this topic to learn how to create a Persistent Chat Server administrator role to enable initial configuration and management of Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="e62f6-105">在商務用 Skype Server 中，執行特定工作的使用者必須指派為一或多個特定群組的成員。</span><span class="sxs-lookup"><span data-stu-id="e62f6-105">In Skype for Business Server, users who perform specific tasks must be assigned as members of one or more specific groups.</span></span> <span data-ttu-id="e62f6-106">Role-Based 存取控制 (RBAC) 是用來授與許可權的方式，方法是指派使用者至預先定義的商務用 Skype Server 系統管理角色。</span><span class="sxs-lookup"><span data-stu-id="e62f6-106">Role-Based Access Control (RBAC) is used to grant privileges by assigning users to predefined Skype for Business Server administrative roles.</span></span> <span data-ttu-id="e62f6-107">這些角色會對應至 Active Directory 網域服務中的通用安全性群組。</span><span class="sxs-lookup"><span data-stu-id="e62f6-107">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="e62f6-108">Persistent Chat 系統管理員安全性群組的成員（CsPersistentChatAdministrator）會被授與 Persistent Chat Server Cmdlet 的存取權，可使用商務用 Skype Server 管理命令介面或商務用 Skype Server 控制台執行。</span><span class="sxs-lookup"><span data-stu-id="e62f6-108">Members of the Persistent Chat Administrator security group, CsPersistentChatAdministrator, are granted access to the Persistent Chat Server cmdlets, which can be executed using either the Skype for Business Server Management Shell or the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="e62f6-109">在設定及管理 Persistent Chat Server 之前，請確定適當的使用者權限及許可權已存在，而且將充當 Persistent Chat 系統管理員的任何使用者都已新增至 Persistent Chat Administrator 安全性群組。</span><span class="sxs-lookup"><span data-stu-id="e62f6-109">Before configuring and administering Persistent Chat Server, be sure that the appropriate user rights and permissions are in place, and that any users who will act as Persistent Chat administrators are added to the Persistent Chat Administrator security group.</span></span>
  
> [!NOTE] 
> <span data-ttu-id="e62f6-110">商務用 Skype Server 2015 仍提供持續聊天，但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="e62f6-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="e62f6-111">小組中提供相同的功能。</span><span class="sxs-lookup"><span data-stu-id="e62f6-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="e62f6-112">如需詳細資訊，請參閱 [Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。</span><span class="sxs-lookup"><span data-stu-id="e62f6-112">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="e62f6-113">如果您需要使用持續聊天，您可以選擇將需要這項功能的使用者遷移至小組，或是繼續使用商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="e62f6-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

## <a name="create-a-persistent-chat-administrator"></a><span data-ttu-id="e62f6-114">建立常設聊天室系統管理員</span><span class="sxs-lookup"><span data-stu-id="e62f6-114">Create a Persistent Chat administrator</span></span>

<span data-ttu-id="e62f6-115">若要將使用者新增至 [Persistent Chat Administrator] 安全性群組，請 CsPersistentChatAdministrator，執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="e62f6-115">To add a user to the Persistent Chat Administrator security group, CsPersistentChatAdministrator, perform the following steps:</span></span>
  
1. <span data-ttu-id="e62f6-116">使用有權修改 Active Directory 群組成員資格的帳戶，登入已安裝 Active Directory 使用者和電腦的電腦。</span><span class="sxs-lookup"><span data-stu-id="e62f6-116">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers have been installed.</span></span>
    
2. <span data-ttu-id="e62f6-117">依序按一下 [開始]、[所有程式]、[系統管理工具] 及 [Active Directory 使用者及電腦]。</span><span class="sxs-lookup"><span data-stu-id="e62f6-117">Click Start, click All Programs, click Administrative Tools, and then click Active Directory Users and Computers.</span></span>
    
3. <span data-ttu-id="e62f6-118">在 [Active Directory 使用者及電腦] 中，展開您的網功能變數名稱稱，然後按一下 [使用者] 容器。</span><span class="sxs-lookup"><span data-stu-id="e62f6-118">In Active Directory Users and Computers, expand the name of your domain and click the Users container.</span></span>
    
4. <span data-ttu-id="e62f6-119">以滑鼠右鍵按一下安全性群組 CsPersistentChatAdministrator，然後按一下 [屬性]。</span><span class="sxs-lookup"><span data-stu-id="e62f6-119">Right-click the security group CsPersistentChatAdministrator, and then click Properties.</span></span>
    
5. <span data-ttu-id="e62f6-120">在 [屬性] 對話方塊的 [成員] 索引標籤上，按一下 [新增]。</span><span class="sxs-lookup"><span data-stu-id="e62f6-120">In the Properties dialog box, on the Members tab, click Add.</span></span>
    
6. <span data-ttu-id="e62f6-121">在 [選取使用者、電腦、連絡人或群組] 對話方塊的 [輸入物件名稱來選取] 方塊中，輸入要新增至群組的使用者名稱或顯示名稱，然後按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="e62f6-121">In the Select Users, Computers, Contact, or Groups dialog box, type the user name or display name of the user to be added to the group in the Enter the object names to select box and then click OK.</span></span>
    
7. <span data-ttu-id="e62f6-122">在 [內容] 對話方塊中，按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="e62f6-122">In the Properties dialog box, click OK.</span></span>
    

