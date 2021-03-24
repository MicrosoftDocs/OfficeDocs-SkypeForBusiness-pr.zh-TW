---
title: Skype 會議室系統網域加入考慮
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: 閱讀此主題以瞭解如何將 Skype 室系統裝置電腦加入您的網域。
ms.openlocfilehash: cf98f98a7294ead0920b3d6b07b00879cbfe15f3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093567"
---
# <a name="skype-room-system-domain-joining-considerations"></a><span data-ttu-id="18ad5-103">Skype 會議室系統網域加入考慮</span><span class="sxs-lookup"><span data-stu-id="18ad5-103">Skype Room System domain joining considerations</span></span>
 
<span data-ttu-id="18ad5-104">閱讀此主題以瞭解如何將 Skype 室系統裝置電腦加入您的網域。</span><span class="sxs-lookup"><span data-stu-id="18ad5-104">Read this topic to learn how to join a Skype Room System appliance PC to your domain.</span></span>
  
## <a name="domain-joining-considerations"></a><span data-ttu-id="18ad5-105">網域聯結考量</span><span class="sxs-lookup"><span data-stu-id="18ad5-105">Domain joining considerations</span></span>

<span data-ttu-id="18ad5-106">您可以將 Skype 室系統裝置電腦加入至 Active Directory 網域，或將其保留在工作組中。</span><span class="sxs-lookup"><span data-stu-id="18ad5-106">You can join the Skype Room System appliance PC to the Active Directory domain or leave it in a Workgroup.</span></span> <span data-ttu-id="18ad5-107">作出這項決策之前，請先考慮下列幾點：</span><span class="sxs-lookup"><span data-stu-id="18ad5-107">Consider the following points before making this decision:</span></span>
  
- <span data-ttu-id="18ad5-108">加入網域的 Skype 室系統裝置電腦可協助您自動匯入組織的私人根憑證鏈。</span><span class="sxs-lookup"><span data-stu-id="18ad5-108">Domain-joining the Skype Room System appliance PC helps in importing your organization's private root certificate chain automatically.</span></span>
    
- <span data-ttu-id="18ad5-109">加入網域的 Skype 室系統裝置電腦可讓您授與網域使用者和群組的管理許可權。</span><span class="sxs-lookup"><span data-stu-id="18ad5-109">Domain-joining the Skype Room System appliance PC enables you to grant domain users and groups administrative rights.</span></span> <span data-ttu-id="18ad5-110">這樣一來，您就不需要記住本機電腦層級管理員帳戶密碼。</span><span class="sxs-lookup"><span data-stu-id="18ad5-110">By doing so, you will not have to remember the local machine level administrator account password.</span></span>
    
- <span data-ttu-id="18ad5-111">當您將 Skype 會議室系統裝置電腦加入網域時，必須建立個別的組織單位 (OU) ，這樣您就可以在所有的 Skype 會議室系統電腦物件所在的 OU 中提供「群組原則」物件 (GPO) 排除專案。</span><span class="sxs-lookup"><span data-stu-id="18ad5-111">When you join an Skype Room System appliance PC to the domain, it is required that you create a separate Organizational Unit (OU), so that you can provide Group Policy Object (GPO) exclusions to the OU where all the Skype Room System machine objects reside.</span></span> <span data-ttu-id="18ad5-112">當您執行此動作時，請先在 OU 中建立電腦物件，然後再將 Skype 室系統裝置電腦加入網域。</span><span class="sxs-lookup"><span data-stu-id="18ad5-112">When you do this, create machine objects in the OU before joining the Skype Room System appliance PC to the domain.</span></span>
    
- <span data-ttu-id="18ad5-113">許多組織都有下列 Gpo，這會影響 Skype 室系統裝置電腦的功能。</span><span class="sxs-lookup"><span data-stu-id="18ad5-113">Many organizations have the following GPOs, which affect Skype Room System appliance PC functions.</span></span> <span data-ttu-id="18ad5-114">確定您覆寫或封鎖 Skype 會議室系統中這些 Gpo 的繼承 OU:</span><span class="sxs-lookup"><span data-stu-id="18ad5-114">Ensure that you override or block the inheritance of these GPOs in the Skype Room System OU:</span></span> 
    
  - <span data-ttu-id="18ad5-115">登入會話的超時 (自動鎖定) </span><span class="sxs-lookup"><span data-stu-id="18ad5-115">Timeout of logon sessions (auto lockout)</span></span>
    
  - <span data-ttu-id="18ad5-116">電源管理相關原則</span><span class="sxs-lookup"><span data-stu-id="18ad5-116">Power management related policies</span></span>
    
  - <span data-ttu-id="18ad5-117">需要其他驗證步驟</span><span class="sxs-lookup"><span data-stu-id="18ad5-117">Requiring additional authentication steps</span></span>
    
  - <span data-ttu-id="18ad5-118">拒絕存取本機磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="18ad5-118">Denying access to local drives</span></span>
    
  - <span data-ttu-id="18ad5-119">提示使用者輸入慢速網路連接</span><span class="sxs-lookup"><span data-stu-id="18ad5-119">Prompting users for slow network connections</span></span>
    
  - <span data-ttu-id="18ad5-120">登入時啟動特定程式</span><span class="sxs-lookup"><span data-stu-id="18ad5-120">Start a certain program at logon</span></span>
    
  - <span data-ttu-id="18ad5-121">在所有加入網域的機器上建立另一個網域使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="18ad5-121">Create another domain user account on all domain-joined machines.</span></span>
    
  - <span data-ttu-id="18ad5-122">將 Windows 更新推送至 Skype 室系統</span><span class="sxs-lookup"><span data-stu-id="18ad5-122">Push Windows Update to Skype Room System</span></span>
    
- <span data-ttu-id="18ad5-123">或者，您也可以決定在工作組中留下裝置電腦。</span><span class="sxs-lookup"><span data-stu-id="18ad5-123">Alternatively, you might decide to leave the appliance PC in the workgroup.</span></span> <span data-ttu-id="18ad5-124">就像使用桌面商務用 Skype 用戶端一樣，這需要您手動匯入 Skype 聊天室系統裝置電腦上的根憑證鏈。</span><span class="sxs-lookup"><span data-stu-id="18ad5-124">As with the desktop Skype for Business client, this requires you to manually import the root certificate chain on the Skype Room System appliance PC.</span></span> <span data-ttu-id="18ad5-125">若您的商務用 Skype 部署是使用公用憑證 (例如，Entrust、VeriSign) 等等，您就不需要匯入根憑證鏈。</span><span class="sxs-lookup"><span data-stu-id="18ad5-125">You're not required to import the root certificate chain if your Skype for Business deployment is using a public certificate (for example, Entrust, VeriSign, and so on).</span></span> 
    
<span data-ttu-id="18ad5-126">如果您打算將 Skype 會議室系統機器加入網域，請避免無意中將 Skype 聊天室系統機器加入非預期的 OU，而不是 Gpo 中，請確定您加入正確的 OU。</span><span class="sxs-lookup"><span data-stu-id="18ad5-126">If you plan to join Skype Room System machines to the domain, to avoid joining Skype Room System machine inadvertently to an unintended OU, which may not be free from GPOs, please ensure you join the correct OU.</span></span> <span data-ttu-id="18ad5-127">您可以從 Skype 聊天室系統機器使用下列 Cmdlet，以加入正確的 OU，而且不會收到可能封鎖 LRS 功能的 Gpo。</span><span class="sxs-lookup"><span data-stu-id="18ad5-127">You can use the following cmdlet from the Skype Room System machine to join in the correct OU and does not receive GPOs that might block LRS functionality.</span></span> <span data-ttu-id="18ad5-128">請與系統管理員或 OEM 合作夥伴聯繫，以執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="18ad5-128">Contact your system administrator or OEM partner to run these cmdlet:</span></span>
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

<span data-ttu-id="18ad5-129">即使您建立個別的 OU 和封鎖繼承，有些原則也有可能導致較高等級的問題。</span><span class="sxs-lookup"><span data-stu-id="18ad5-129">Even if you create a separate OU and block inheritance, there are some policies which could cause issues at a higher level.</span></span> <span data-ttu-id="18ad5-130">[不含覆寫的群組原則] 設定會勝過使用 [封鎖原則繼承] 設定的 OU。</span><span class="sxs-lookup"><span data-stu-id="18ad5-130">A Group Policy with No Override setting beats an OU with a Block Policy Inheritance setting.</span></span> <span data-ttu-id="18ad5-131">如需詳細資訊，請參閱與群組原則檔中的 [封鎖原則繼承](/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) 一文中的「沒有覆寫」一文。</span><span class="sxs-lookup"><span data-stu-id="18ad5-131">For more information, see the article [No Override as Compared to Block Policy Inheritance](/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) in the Group Policy documentation.</span></span>
  
<span data-ttu-id="18ad5-132">您可能會有多種方法可解決這些問題。</span><span class="sxs-lookup"><span data-stu-id="18ad5-132">You may have multiple approaches to solving these problems.</span></span> <span data-ttu-id="18ad5-133">我們建議您與您的 Active Directory 專家協商，以確保您已在具有適當 GPO 設定的 OU 中提供，或是至少在先前描述的原則不存在的 OU 中提供。</span><span class="sxs-lookup"><span data-stu-id="18ad5-133">We advise you to consult with your Active Directory experts to ensure you are provided with an OU that has appropriate GPO settings, or at least an OU in which the previously described policies do not exist.</span></span> <span data-ttu-id="18ad5-134">建議您為 Skype 會議室系統裝置啟用 [服務品質 (QoS) ]。</span><span class="sxs-lookup"><span data-stu-id="18ad5-134">It is advised to enable Quality of Service (QoS) for Skype Room System devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="18ad5-135">另請參閱</span><span class="sxs-lookup"><span data-stu-id="18ad5-135">See also</span></span>
  
[<span data-ttu-id="18ad5-136">裝置組態：建立新的或編輯現有組態</span><span class="sxs-lookup"><span data-stu-id="18ad5-136">Device Configuration: Create New or Edit Existing</span></span>](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[<span data-ttu-id="18ad5-137">管理服務品質</span><span class="sxs-lookup"><span data-stu-id="18ad5-137">Managing Quality of Service</span></span>](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)