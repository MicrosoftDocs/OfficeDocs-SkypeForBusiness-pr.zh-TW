---
title: Skype 會議室系統網域加入考慮
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: 若要瞭解如何將 Skype 會議室系統裝置電腦加入您的網域，請閱讀本主題。
ms.openlocfilehash: 49e8c89ed9ddbbd579e7ed30fec6b98a933e3a3f
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768926"
---
# <a name="skype-room-system-domain-joining-considerations"></a><span data-ttu-id="94ce0-103">Skype 會議室系統網域加入考慮</span><span class="sxs-lookup"><span data-stu-id="94ce0-103">Skype Room System domain joining considerations</span></span>
 
<span data-ttu-id="94ce0-104">若要瞭解如何將 Skype 會議室系統裝置電腦加入您的網域，請閱讀本主題。</span><span class="sxs-lookup"><span data-stu-id="94ce0-104">Read this topic to learn how to join a Skype Room System appliance PC to your domain.</span></span>
  
## <a name="domain-joining-considerations"></a><span data-ttu-id="94ce0-105">網域加入考慮</span><span class="sxs-lookup"><span data-stu-id="94ce0-105">Domain joining considerations</span></span>

<span data-ttu-id="94ce0-106">您可以將 Skype 會議室系統裝置電腦加入 Active Directory 網域，或將其留在工作組中。</span><span class="sxs-lookup"><span data-stu-id="94ce0-106">You can join the Skype Room System appliance PC to the Active Directory domain or leave it in a Workgroup.</span></span> <span data-ttu-id="94ce0-107">在進行這項決策前，請先考慮下列幾點：</span><span class="sxs-lookup"><span data-stu-id="94ce0-107">Consider the following points before making this decision:</span></span>
  
- <span data-ttu-id="94ce0-108">網域-加入 Skype 會議室系統裝置電腦可協助您自動匯入貴組織的私人根憑證鏈。</span><span class="sxs-lookup"><span data-stu-id="94ce0-108">Domain-joining the Skype Room System appliance PC helps in importing your organization's private root certificate chain automatically.</span></span>
    
- <span data-ttu-id="94ce0-109">[網域-加入 Skype 會議室系統裝置電腦] 可讓您授與網域使用者和群組的管理許可權。</span><span class="sxs-lookup"><span data-stu-id="94ce0-109">Domain-joining the Skype Room System appliance PC enables you to grant domain users and groups administrative rights.</span></span> <span data-ttu-id="94ce0-110">如此一來，您就不需要記住本機電腦層級的系統管理員帳戶密碼。</span><span class="sxs-lookup"><span data-stu-id="94ce0-110">By doing so, you will not have to remember the local machine level administrator account password.</span></span>
    
- <span data-ttu-id="94ce0-111">當您將 Skype 會議室系統裝置電腦加入網域時，必須建立個別的組織單位（OU），這樣您才能將群組原則物件（GPO）排除專案提供給所有 Skype 會議室系統電腦物件所在的 OU。</span><span class="sxs-lookup"><span data-stu-id="94ce0-111">When you join an Skype Room System appliance PC to the domain, it is required that you create a separate Organizational Unit (OU), so that you can provide Group Policy Object (GPO) exclusions to the OU where all the Skype Room System machine objects reside.</span></span> <span data-ttu-id="94ce0-112">當您這麼做時，請先在 OU 中建立電腦物件，然後再將 Skype 會議室系統裝置電腦加入網域。</span><span class="sxs-lookup"><span data-stu-id="94ce0-112">When you do this, create machine objects in the OU before joining the Skype Room System appliance PC to the domain.</span></span>
    
- <span data-ttu-id="94ce0-113">許多組織都有下列 Gpo，這些 Gpo 會影響 Skype 室系統裝置的電腦功能。</span><span class="sxs-lookup"><span data-stu-id="94ce0-113">Many organizations have the following GPOs, which affect Skype Room System appliance PC functions.</span></span> <span data-ttu-id="94ce0-114">請確定您覆寫或封鎖 Skype 會議室系統 OU 中這些 Gpo 的繼承：</span><span class="sxs-lookup"><span data-stu-id="94ce0-114">Ensure that you override or block the inheritance of these GPOs in the Skype Room System OU:</span></span> 
    
  - <span data-ttu-id="94ce0-115">登入會話超時（自動封鎖）</span><span class="sxs-lookup"><span data-stu-id="94ce0-115">Timeout of logon sessions (auto lockout)</span></span>
    
  - <span data-ttu-id="94ce0-116">與電源管理相關的原則</span><span class="sxs-lookup"><span data-stu-id="94ce0-116">Power management related policies</span></span>
    
  - <span data-ttu-id="94ce0-117">需要其他驗證步驟</span><span class="sxs-lookup"><span data-stu-id="94ce0-117">Requiring additional authentication steps</span></span>
    
  - <span data-ttu-id="94ce0-118">拒絕存取本機磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="94ce0-118">Denying access to local drives</span></span>
    
  - <span data-ttu-id="94ce0-119">提示使用者進行緩慢的網路連線</span><span class="sxs-lookup"><span data-stu-id="94ce0-119">Prompting users for slow network connections</span></span>
    
  - <span data-ttu-id="94ce0-120">在登入時啟動特定程式</span><span class="sxs-lookup"><span data-stu-id="94ce0-120">Start a certain program at logon</span></span>
    
  - <span data-ttu-id="94ce0-121">在所有加入網域的電腦上建立另一個網域使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="94ce0-121">Create another domain user account on all domain-joined machines.</span></span>
    
  - <span data-ttu-id="94ce0-122">將 Windows 更新推送至 Skype 會議室系統</span><span class="sxs-lookup"><span data-stu-id="94ce0-122">Push Windows Update to Skype Room System</span></span>
    
- <span data-ttu-id="94ce0-123">或者，您也可以決定將裝置電腦留在工作組中。</span><span class="sxs-lookup"><span data-stu-id="94ce0-123">Alternatively, you might decide to leave the appliance PC in the workgroup.</span></span> <span data-ttu-id="94ce0-124">就像桌面商務用 Skype 用戶端一樣，這需要您手動匯入 Skype 會議室 System 裝置電腦上的根憑證鏈。</span><span class="sxs-lookup"><span data-stu-id="94ce0-124">As with the desktop Skype for Business client, this requires you to manually import the root certificate chain on the Skype Room System appliance PC.</span></span> <span data-ttu-id="94ce0-125">如果您的商務用 Skype 部署是使用公用憑證（例如，Entrust、VeriSign 等），就不需要匯入根憑證鏈。</span><span class="sxs-lookup"><span data-stu-id="94ce0-125">You're not required to import the root certificate chain if your Skype for Business deployment is using a public certificate (for example, Entrust, VeriSign, and so on).</span></span> 
    
<span data-ttu-id="94ce0-126">如果您打算將 Skype 會議室系統電腦加入網域，以避免將 Skype 會議室系統電腦不小心加入非預期的 OU （可能無法從 Gpo 中移除），請確認您加入正確的 OU。</span><span class="sxs-lookup"><span data-stu-id="94ce0-126">If you plan to join Skype Room System machines to the domain, to avoid joining Skype Room System machine inadvertently to an unintended OU, which may not be free from GPOs, please ensure you join the correct OU.</span></span> <span data-ttu-id="94ce0-127">您可以使用來自 Skype 聊天室系統電腦的下列 Cmdlet，在正確的 OU 中加入，且不會收到可能會封鎖 LRS 功能的 Gpo。</span><span class="sxs-lookup"><span data-stu-id="94ce0-127">You can use the following cmdlet from the Skype Room System machine to join in the correct OU and does not receive GPOs that might block LRS functionality.</span></span> <span data-ttu-id="94ce0-128">請與您的系統管理員或 OEM 合作夥伴，以執行這些 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="94ce0-128">Contact your system administrator or OEM partner to run these cmdlet:</span></span>
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

<span data-ttu-id="94ce0-129">即使您建立個別的 OU 和封鎖繼承，仍有一些原則可能會造成較高層面的問題。</span><span class="sxs-lookup"><span data-stu-id="94ce0-129">Even if you create a separate OU and block inheritance, there are some policies which could cause issues at a higher level.</span></span> <span data-ttu-id="94ce0-130">沒有 [覆寫] 設定的群組原則會使用 [封鎖原則繼承] 設定來擊敗 OU。</span><span class="sxs-lookup"><span data-stu-id="94ce0-130">A Group Policy with No Override setting beats an OU with a Block Policy Inheritance setting.</span></span> <span data-ttu-id="94ce0-131">如需詳細資訊，請參閱在群組原則檔中與[封鎖原則繼承](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10))一文中的「不改寫」。</span><span class="sxs-lookup"><span data-stu-id="94ce0-131">For more information, see the article [No Override as Compared to Block Policy Inheritance](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) in the Group Policy documentation.</span></span>
  
<span data-ttu-id="94ce0-132">您可能有多種方法可以解決這些問題。</span><span class="sxs-lookup"><span data-stu-id="94ce0-132">You may have multiple approaches to solving these problems.</span></span> <span data-ttu-id="94ce0-133">我們建議您與 Active Directory 專家協商，以確保您有提供適當 GPO 設定的 OU，或至少有先前描述之原則不存在的 OU。</span><span class="sxs-lookup"><span data-stu-id="94ce0-133">We advise you to consult with your Active Directory experts to ensure you are provided with an OU that has appropriate GPO settings, or at least an OU in which the previously described policies do not exist.</span></span> <span data-ttu-id="94ce0-134">建議啟用 Skype 會議室系統裝置的服務品質（QoS）。</span><span class="sxs-lookup"><span data-stu-id="94ce0-134">It is advised to enable Quality of Service (QoS) for Skype Room System devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="94ce0-135">另請參閱</span><span class="sxs-lookup"><span data-stu-id="94ce0-135">See also</span></span>
  
[<span data-ttu-id="94ce0-136">裝置組態：建立新的或編輯現有組態</span><span class="sxs-lookup"><span data-stu-id="94ce0-136">Device Configuration: Create New or Edit Existing</span></span>](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[<span data-ttu-id="94ce0-137">管理服務品質</span><span class="sxs-lookup"><span data-stu-id="94ce0-137">Managing Quality of Service</span></span>](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)
