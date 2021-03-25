---
title: Skype 會議室系統網域加入考慮
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
ms.collection:
- M365-collaboration
description: 系統管理員可以瞭解如何將 Skype Room System 裝置電腦加入 Active Directory 網域，以及這麼做的考慮。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c322819fb765e05cead793c95b5e3b6af2d2a180
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117551"
---
<!-- This asset missed in the rebrand, and honestly not sure if it's worth keeping.   -->

# <a name="skype-room-system-domain-joining-considerations"></a><span data-ttu-id="75eb6-103">Skype 會議室系統網域加入考慮</span><span class="sxs-lookup"><span data-stu-id="75eb6-103">Skype Room System domain joining considerations</span></span>
 
<span data-ttu-id="75eb6-104">請閱讀本主題，瞭解如何將 Skype Room System 裝置電腦加入您的網域。</span><span class="sxs-lookup"><span data-stu-id="75eb6-104">Read this topic to learn how to join a Skype Room System appliance PC to your domain.</span></span>
  
## <a name="domain-joining-considerations"></a><span data-ttu-id="75eb6-105">網域加入考慮</span><span class="sxs-lookup"><span data-stu-id="75eb6-105">Domain joining considerations</span></span>

<span data-ttu-id="75eb6-106">您可以將 Skype Room System 裝置電腦加入 Active Directory 網域，或將它留在工作組中。</span><span class="sxs-lookup"><span data-stu-id="75eb6-106">You can join the Skype Room System appliance PC to the Active Directory domain or leave it in a Workgroup.</span></span> <span data-ttu-id="75eb6-107">在做出此決策之前，請考慮下列各點：</span><span class="sxs-lookup"><span data-stu-id="75eb6-107">Consider the following points before making this decision:</span></span>
  
- <span data-ttu-id="75eb6-108">網域加入 Skype Room System 裝置電腦可協助自動導入貴組織的專用根憑證鏈。</span><span class="sxs-lookup"><span data-stu-id="75eb6-108">Domain-joining the Skype Room System appliance PC helps in importing your organization's private root certificate chain automatically.</span></span>
- <span data-ttu-id="75eb6-109">網域加入 Skype Room System 裝置電腦可讓您授予網域使用者和群組系統管理許可權。</span><span class="sxs-lookup"><span data-stu-id="75eb6-109">Domain-joining the Skype Room System appliance PC enables you to grant domain users and groups administrative rights.</span></span> <span data-ttu-id="75eb6-110">如此一來，您就不需要記住本機電腦層級系統管理員帳戶密碼。</span><span class="sxs-lookup"><span data-stu-id="75eb6-110">By doing so, you will not have to remember the local machine level administrator account password.</span></span>
- <span data-ttu-id="75eb6-111">當您將 Skype Room System 裝置電腦加入網域時，您必須建立個別的組織單位 (OU) ，這樣您才能將群組原則物件 (GPO) 排除功能提供給所有 Skype 會議室系統電腦物件所在的 OU。</span><span class="sxs-lookup"><span data-stu-id="75eb6-111">When you join a Skype Room System appliance PC to the domain, it is required that you create a separate Organizational Unit (OU), so that you can provide Group Policy Object (GPO) exclusions to the OU where all the Skype Room System machine objects reside.</span></span> <span data-ttu-id="75eb6-112">當您這麼做時，在加入 Skype Room System 裝置電腦至網域之前，先在 OU 中建立電腦物件。</span><span class="sxs-lookup"><span data-stu-id="75eb6-112">When you do this, create machine objects in the OU before joining the Skype Room System appliance PC to the domain.</span></span>
- <span data-ttu-id="75eb6-113">許多組織都有下列 GPO，這會影響 Skype Room System 裝置 PC 功能。</span><span class="sxs-lookup"><span data-stu-id="75eb6-113">Many organizations have the following GPOs, which affect Skype Room System appliance PC functions.</span></span> <span data-ttu-id="75eb6-114">確保您在 Skype 會議室系統 OU 中重寫或封鎖這些 GPO 的繼承：</span><span class="sxs-lookup"><span data-stu-id="75eb6-114">Ensure that you override or block the inheritance of these GPOs in the Skype Room System OU:</span></span>

  - <span data-ttu-id="75eb6-115">登入會話的超時 (自動鎖定) </span><span class="sxs-lookup"><span data-stu-id="75eb6-115">Timeout of logon sessions (auto lockout)</span></span>
  - <span data-ttu-id="75eb6-116">與電源管理相關的政策</span><span class="sxs-lookup"><span data-stu-id="75eb6-116">Policies related to power management</span></span>
  - <span data-ttu-id="75eb6-117">需要其他驗證步驟</span><span class="sxs-lookup"><span data-stu-id="75eb6-117">Requiring additional authentication steps</span></span>
  - <span data-ttu-id="75eb6-118">拒絕存取本地磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="75eb6-118">Denying access to local drives</span></span>
  - <span data-ttu-id="75eb6-119">提示使用者網路連接速度緩慢</span><span class="sxs-lookup"><span data-stu-id="75eb6-119">Prompting users for slow network connections</span></span>
  - <span data-ttu-id="75eb6-120">登入時啟動特定程式</span><span class="sxs-lookup"><span data-stu-id="75eb6-120">Start a certain program at logon</span></span>
  - <span data-ttu-id="75eb6-121">在所有加入網域的電腦上建立另一個網域使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="75eb6-121">Create another domain user account on all domain-joined machines.</span></span>
  - <span data-ttu-id="75eb6-122">將 Windows Update 推送到 Skype 會議室系統</span><span class="sxs-lookup"><span data-stu-id="75eb6-122">Push Windows Update to Skype Room System</span></span>
    
- <span data-ttu-id="75eb6-123">或者，您可能會決定將裝置電腦留在工作組中。</span><span class="sxs-lookup"><span data-stu-id="75eb6-123">Alternatively, you might decide to leave the appliance PC in the workgroup.</span></span> <span data-ttu-id="75eb6-124">與桌上出版 Microsoft Teams 或商務用 Skype 用戶端一樣，這要求您在 Skype Room System 裝置 PC 上手動導入根憑證鏈。</span><span class="sxs-lookup"><span data-stu-id="75eb6-124">As with the desktop Microsoft Teams or Skype for Business client, this requires you to manually import the root certificate chain on the Skype Room System appliance PC.</span></span> <span data-ttu-id="75eb6-125">如果您的部署是使用公用憑證 (例如，委託、VeriSign 等等，則不需要將根憑證鏈) 。</span><span class="sxs-lookup"><span data-stu-id="75eb6-125">You're not required to import the root certificate chain if your deployment is using a public certificate (for example, Entrust, VeriSign, and so on).</span></span> 
    
<span data-ttu-id="75eb6-126">如果您打算將 Skype Room System 電腦加入網域，為了避免不小心將 Skype 會議室系統電腦加入非預期的 OU ，而此 OU 可能並非 GPO 所提供，請確定您加入正確的 OU。</span><span class="sxs-lookup"><span data-stu-id="75eb6-126">If you plan to join Skype Room System machines to the domain, to avoid joining Skype Room System machine inadvertently to an unintended OU, which may not be free from GPOs, please ensure you join the correct OU.</span></span> <span data-ttu-id="75eb6-127">您可以使用 Skype Room System 電腦中的下列 Cmdlet 加入正確的 OU，而且不會收到可能會封鎖 LRS 功能的 GPO。</span><span class="sxs-lookup"><span data-stu-id="75eb6-127">You can use the following cmdlet from the Skype Room System machine to join in the correct OU and does not receive GPOs that might block LRS functionality.</span></span> <span data-ttu-id="75eb6-128">請與您的系統管理員或 OEM 合作夥伴聯繫，以執行這些 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="75eb6-128">Contact your system administrator or OEM partner to run these cmdlets:</span></span>
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

<span data-ttu-id="75eb6-129">即使您建立個別的 OU 和封鎖繼承，也有一些可能會導致較高層級的問題。</span><span class="sxs-lookup"><span data-stu-id="75eb6-129">Even if you create a separate OU and block inheritance, there are some policies that could cause issues at a higher level.</span></span> <span data-ttu-id="75eb6-130">具有 No Override 設定的群組原則會以封鎖策略繼承設定比對 OU。</span><span class="sxs-lookup"><span data-stu-id="75eb6-130">A Group Policy with No Override setting beats an OU with a Block Policy Inheritance setting.</span></span> <span data-ttu-id="75eb6-131">若要詳細資訊，請參閱群組原則檔中與封鎖 [策略繼承](/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) 比較的無重寫。</span><span class="sxs-lookup"><span data-stu-id="75eb6-131">For more information, see [No Override as Compared to Block Policy Inheritance](/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) in the Group Policy documentation.</span></span>
  
<span data-ttu-id="75eb6-132">您可能有多種方法可以解決這些問題。</span><span class="sxs-lookup"><span data-stu-id="75eb6-132">You may have multiple approaches to solving these problems.</span></span> <span data-ttu-id="75eb6-133">我們建議您諮詢 Active Directory 專家，以確保您獲得具有適當 GPO 設定的 OU，或至少提供不存在先前所述之策略的 OU。</span><span class="sxs-lookup"><span data-stu-id="75eb6-133">We advise you to consult with your Active Directory experts to ensure that you are provided with an OU that has appropriate GPO settings, or at least an OU in which the previously described policies do not exist.</span></span> <span data-ttu-id="75eb6-134">我們建議您針對 Skype 會議室系統裝置啟用 QoS (QoS) 服務品質。</span><span class="sxs-lookup"><span data-stu-id="75eb6-134">We advise to enabling Quality of Service (QoS) for Skype Room System devices.</span></span>

## <a name="related-topics"></a><span data-ttu-id="75eb6-135">相關主題</span><span class="sxs-lookup"><span data-stu-id="75eb6-135">Related topics</span></span>
  
[<span data-ttu-id="75eb6-136">裝置組態：建立新的或編輯現有組態</span><span class="sxs-lookup"><span data-stu-id="75eb6-136">Device Configuration: Create New or Edit Existing</span></span>](/skypeforbusiness/help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[<span data-ttu-id="75eb6-137">管理服務品質</span><span class="sxs-lookup"><span data-stu-id="75eb6-137">Managing Quality of Service</span></span>](/skypeforbusiness/plan-your-deployment/network-requirements/network-requirements#managing-quality-of-service)