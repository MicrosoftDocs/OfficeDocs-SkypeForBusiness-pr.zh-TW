---
title: 建立商務用 Skype Server 控制台系統管理員
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployMainCreateCSCPAdmin
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3312926a-4671-4030-bb92-90ac24c778dd
description: 若要授與商務用 Skype Server 2015 的存取權，請執行下列動作：
ms.openlocfilehash: fc192db37cb0808326d1098d396f0d2b31642537
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41687716"
---
# <a name="create-skype-for-business-server-control-panel-administrators"></a><span data-ttu-id="c748c-103">建立商務用 Skype Server 控制台系統管理員</span><span class="sxs-lookup"><span data-stu-id="c748c-103">Create Skype for Business Server Control Panel Administrators</span></span>
 
<span data-ttu-id="c748c-104">若要授與商務用 Skype Server 2015 的存取權，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="c748c-104">To grant access to the Skype for Business Server 2015, do the following:</span></span>
  
1. <span data-ttu-id="c748c-105">使用 Domain Admins 群組成員或 RTCUniversalServerAdmins 群組成員的身分登入。</span><span class="sxs-lookup"><span data-stu-id="c748c-105">Log on as a member of the Domain Admins group or the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="c748c-106">開啟 [Active Directory 使用者及電腦]\*\*\*\*，展開網域，以滑鼠右鍵按一下 [使用者] \*\*\*\* 容器，然後按一下 [內容]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c748c-106">Open **Active Directory Users and Computers**, expand your domain, right-click the **Users** container, and then click **Properties**.</span></span>
    
3. <span data-ttu-id="c748c-107">在 [CSAdministrator 內容] \*\*\*\* 中，按一下 [成員] \*\*\*\* 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="c748c-107">In **CSAdministrator Properties**, click the **Members** tab.</span></span>
    
4. <span data-ttu-id="c748c-p101">在 [成員] 索引標籤上，按一下 [新增]\*\*\*\*。在 [選取使用者、連絡人、電腦、服務帳戶或群組] \*\*\*\* 中，找到 [輸入要選取的物件名稱]\*\*\*\*。輸入要新增到 CSAdministrators 群組的使用者名稱或群組名稱。按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c748c-p101">On the Members tab, click **Add**. In **Select Users, Contacts, Computers, Service Accounts, or Groups**, locate the **Enter the object names to select**. Type the user name(s) or group name(s) to add to the group CSAdministrators. Click **OK**.</span></span>
    
5. <span data-ttu-id="c748c-p102">在 [成員] 索引標籤上，確認您選取的使用者或群組已存在。按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c748c-p102">On the Members tab, confirm that the users or groups that you selected are present. Click **OK**.</span></span>
    
> [!TIP]
> <span data-ttu-id="c748c-114">商務用 Skype Server 的 [控制台] 是一個以角色為基礎的存取控制工具。</span><span class="sxs-lookup"><span data-stu-id="c748c-114">The Skype for Business Server Control Panel is a role-based access control tool.</span></span> <span data-ttu-id="c748c-115">[CsAdministrator] 群組中的成員資格可讓使用商務用 Skype Server 控制台的使用者完全控制所有可用的設定功能。</span><span class="sxs-lookup"><span data-stu-id="c748c-115">Membership in the CsAdministrator group gives a user who is using the Skype for Business Server Control Panel full control for all the configuration functions available.</span></span> <span data-ttu-id="c748c-116">有些其他的角色是針對特定功能而設計。</span><span class="sxs-lookup"><span data-stu-id="c748c-116">There are other roles available that are designed for specific functions.</span></span> <span data-ttu-id="c748c-117">您不需要針對商務用 Skype Server 啟用使用者，就能成為管理群組的成員。</span><span class="sxs-lookup"><span data-stu-id="c748c-117">Users do not have to be enabled for Skype for Business Server in order to be made members of the management groups.</span></span> 
  
<span data-ttu-id="c748c-118">其他角色包括：</span><span class="sxs-lookup"><span data-stu-id="c748c-118">Other roles include:</span></span>
  
- <span data-ttu-id="c748c-119">**CsArchiving：** 此群組的成員可以執行所有的存檔功能，例如設定及管理封存伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="c748c-119">**CsArchiving:** Members of this group can perform all archiving functions, such as configuring and managing the Archiving Server role.</span></span>
    
- <span data-ttu-id="c748c-p104">**CsHelpDesk：** 這個群組的成員可以檢視設定和部署，包括使用者內容及原則。成員也可以執行特定的疑難排解工作。</span><span class="sxs-lookup"><span data-stu-id="c748c-p104">**CsHelpDesk:** Members of this group can view the configuration and deployment, including user properties and policies. Members can also perform specific troubleshooting tasks.</span></span>
    
- <span data-ttu-id="c748c-p105">**CsLocationAdministrator：** 成員具有與增強型 9-1-1 (E9-1-1) 管理相關聯的最低層級使用者權利。他們可以建立 E9-1-1 位置及網路識別碼，並在部署中建立其關聯。</span><span class="sxs-lookup"><span data-stu-id="c748c-p105">**CsLocationAdministrator:** Members have the lowest level of user rights associated with Enhanced 9-1-1 (E9-1-1) management. They can create E9-1-1 locations and network identifiers and associate those in the deployment.</span></span>
    
- <span data-ttu-id="c748c-124">**CsResponseGroupAdministrator：** 成員可以管理和設定回應群組服務。</span><span class="sxs-lookup"><span data-stu-id="c748c-124">**CsResponseGroupAdministrator:** Members can manage and configure the Response Group service.</span></span>
    
- <span data-ttu-id="c748c-125">**CsServerAdministrator：** 成員可以管理、監視及疑難排解所有執行商務用 Skype Server 的伺服器。</span><span class="sxs-lookup"><span data-stu-id="c748c-125">**CsServerAdministrator:** Members can manage, monitor, and troubleshoot all servers running Skype for Business Server.</span></span>
    
- <span data-ttu-id="c748c-126">**CsUserAdministrator：** 成員可以管理、啟用與停用使用者，以及指派現有的原則給使用者。</span><span class="sxs-lookup"><span data-stu-id="c748c-126">**CsUserAdministrator:** Members can manage, enable and disable users, and assign existing policies to users.</span></span>
    
- <span data-ttu-id="c748c-127">**CsViewOnlyAdministrator：** 成員可以查看伺服器資訊的部署與設定。</span><span class="sxs-lookup"><span data-stu-id="c748c-127">**CsViewOnlyAdministrator:** Members can view the deployment and configuration of the server information.</span></span> <span data-ttu-id="c748c-128">這個成員資格可讓成員監視執行商務用 Skype Server 2015 的伺服器的健康情況。</span><span class="sxs-lookup"><span data-stu-id="c748c-128">This membership enables a member to monitor the health of the servers running Skype for Business Server 2015.</span></span>
    
- <span data-ttu-id="c748c-129">**CsVoiceAdministrator：** 成員可以在商務用 Skype Server 中建立、設定及管理語音相關設定。</span><span class="sxs-lookup"><span data-stu-id="c748c-129">**CsVoiceAdministrator:** Members can create, configure, and manage voice-related settings in Skype for Business Server.</span></span>
    
<span data-ttu-id="c748c-130">若要協助保留安全性與角色式的存取控制完整性，請將使用者新增至群組，以定義使用者在管理商務用 Skype Server 部署時所執行的角色。</span><span class="sxs-lookup"><span data-stu-id="c748c-130">To help retain security and role-based access control integrity, add users to the groups that define what role the user performs in management of the Skype for Business Server deployment.</span></span>
  

