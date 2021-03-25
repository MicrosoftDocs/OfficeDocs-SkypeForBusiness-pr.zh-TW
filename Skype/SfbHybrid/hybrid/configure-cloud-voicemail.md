---
title: 為內部部署使用者設定雲端語音信箱服務
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
ms.date: 2/11/2019
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 有關為位於商務用 Skype Server 上之使用者執行雲端式語音信箱的指示。
ms.openlocfilehash: a9c308189a5dc70c85382f638f30f52c0ac69bdb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118982"
---
# <a name="configure-cloud-voicemail-service-for-on-premises-users"></a><span data-ttu-id="d26a2-103">為內部部署使用者設定雲端語音信箱服務</span><span class="sxs-lookup"><span data-stu-id="d26a2-103">Configure Cloud Voicemail service for on-premises users</span></span>

## <a name="overview"></a><span data-ttu-id="d26a2-104">概觀</span><span class="sxs-lookup"><span data-stu-id="d26a2-104">Overview</span></span> 
<span data-ttu-id="d26a2-105">本文說明如何為商務用 Skype 內部部署使用者設定 Microsoft Cloud 語音信箱服務。</span><span class="sxs-lookup"><span data-stu-id="d26a2-105">This article describes how to configure Microsoft Cloud Voicemail service for your Skype for Business on-premises users.</span></span>  

<span data-ttu-id="d26a2-106">本文假設您已在支援的拓撲中部署商務用 Skype Server，而且您已滿足設定混合式連線的必要條件。</span><span class="sxs-lookup"><span data-stu-id="d26a2-106">This article assumes that you already have Skype for Business Server deployed in a supported topology, and that you have met the prerequisites for setting up hybrid connectivity.</span></span>

<span data-ttu-id="d26a2-107">如需有關執行雲端語音信箱之好處、規劃考慮和需求的詳細資訊，請參閱 [Plan Cloud 語音信箱服務](plan-cloud-voicemail.md)。</span><span class="sxs-lookup"><span data-stu-id="d26a2-107">For more information about the benefits, planning considerations, and requirements for implementing Cloud Voicemail, see [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span></span>




<span data-ttu-id="d26a2-108">設定雲端語音信箱包含下列工作：</span><span class="sxs-lookup"><span data-stu-id="d26a2-108">Configuring Cloud Voicemail involves the following tasks:</span></span>

1.  <span data-ttu-id="d26a2-109">確定您已符合 [Plan Cloud 語音信箱服務](plan-cloud-voicemail.md)中所述的必要條件。</span><span class="sxs-lookup"><span data-stu-id="d26a2-109">Ensure that you have met the prerequisites as described in [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span></span>

2.  <span data-ttu-id="d26a2-110">確定您已依照 [規劃混合](plan-hybrid-connectivity.md) 式連線和設定 [混合](configure-hybrid-connectivity.md)式連線中所述的方式設定混合式連線能力。</span><span class="sxs-lookup"><span data-stu-id="d26a2-110">Ensure that you have set up hybrid connectivity as described in [Plan hybrid connectivity](plan-hybrid-connectivity.md) and [Configure hybrid connectivity](configure-hybrid-connectivity.md).</span></span> 

3.  <span data-ttu-id="d26a2-111">[將雲端語音信箱設定為前端伺服器上的裝載提供者](#configure-cloud-voicemail-as-the-hosting-provider) ，如本文所述。</span><span class="sxs-lookup"><span data-stu-id="d26a2-111">[Configure Cloud Voicemail as the hosting provider on the Front End Server](#configure-cloud-voicemail-as-the-hosting-provider) as described in this article.</span></span>

4.  <span data-ttu-id="d26a2-112">如本文所述，[設定主控的語音信箱原則](#configure-a-hosted-voicemail-policy)。</span><span class="sxs-lookup"><span data-stu-id="d26a2-112">[Configure a hosted voicemail policy](#configure-a-hosted-voicemail-policy) as described in this article.</span></span>

5.  <span data-ttu-id="d26a2-113">依照本文所述[指派主控的語音信箱原則](#assign-a-hosted-voicemail-policy)。</span><span class="sxs-lookup"><span data-stu-id="d26a2-113">[Assign a hosted voicemail policy](#assign-a-hosted-voicemail-policy) as described in this article.</span></span>

6.  <span data-ttu-id="d26a2-114">如本文所述[，啟用雲端語音信箱的使用者](#enable-a-user-for-cloud-voicemail)。</span><span class="sxs-lookup"><span data-stu-id="d26a2-114">[Enable a user for Cloud Voicemail](#enable-a-user-for-cloud-voicemail) as described in this article.</span></span>


## <a name="configure-cloud-voicemail-as-the-hosting-provider"></a><span data-ttu-id="d26a2-115">將雲端語音信箱設定為主機提供者</span><span class="sxs-lookup"><span data-stu-id="d26a2-115">Configure Cloud Voicemail as the hosting provider</span></span> 

<span data-ttu-id="d26a2-116">您可以使用具有下列參數的 New-CsHostingProvider Cmdlet，將雲端語音信箱設定為前端伺服器上的裝載提供者：</span><span class="sxs-lookup"><span data-stu-id="d26a2-116">You configure Cloud Voicemail as the hosting provider on a Front End Server by using the New-CsHostingProvider cmdlet with the following parameters:</span></span>

- <span data-ttu-id="d26a2-117">**Identity** 為所建立的裝載提供者指定唯一的字串值識別碼;例如，雲端語音信箱。</span><span class="sxs-lookup"><span data-stu-id="d26a2-117">**Identity** specifies a unique string value identifier for the hosting provider that you are creating; for example, Cloud Voicemail.</span></span> 

- <span data-ttu-id="d26a2-118">**Enabled** 會指出網域和裝載提供者之間的網路連線是否已啟用。</span><span class="sxs-lookup"><span data-stu-id="d26a2-118">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="d26a2-119">此參數必須設定為 True。</span><span class="sxs-lookup"><span data-stu-id="d26a2-119">This parameter must be set to True.</span></span>

- <span data-ttu-id="d26a2-120">**EnabledSharedAddressSpace** 指出是否將以共用 SIP 位址空間案例使用裝載提供者。</span><span class="sxs-lookup"><span data-stu-id="d26a2-120">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="d26a2-121">此參數必須設定為 True。</span><span class="sxs-lookup"><span data-stu-id="d26a2-121">This parameter must be set to True.</span></span>

- <span data-ttu-id="d26a2-122">**HostsOCSUsers** 會指出裝載提供者是否是用來主控商務用 Skype 伺服器帳戶。</span><span class="sxs-lookup"><span data-stu-id="d26a2-122">**HostsOCSUsers** indicates whether the hosting provider is used to host Skype for Business Server accounts.</span></span> <span data-ttu-id="d26a2-123">此參數必須設為 False。</span><span class="sxs-lookup"><span data-stu-id="d26a2-123">This parameter must be set to False.</span></span>

- <span data-ttu-id="d26a2-124">**ProxyFQDN** 會指定主機服務提供者所使用之 proxy 伺服器的完整功能變數名稱 (FQDN) ;例如，proxyserver.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="d26a2-124">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider; for example, proxyserver.contoso.com.</span></span> <span data-ttu-id="d26a2-125">如需此資訊，請與您的裝載提供者連絡。</span><span class="sxs-lookup"><span data-stu-id="d26a2-125">Contact your hosting provider for this information.</span></span> <span data-ttu-id="d26a2-126">您無法修改此值。</span><span class="sxs-lookup"><span data-stu-id="d26a2-126">This value cannot be modified.</span></span> <span data-ttu-id="d26a2-127">如果主機服務提供者變更其 proxy 伺服器，您將需要刪除該提供者的專案，然後重新建立。</span><span class="sxs-lookup"><span data-stu-id="d26a2-127">If the hosting provider changes its proxy server, you will need to delete and then re-create the entry for that provider.</span></span>

- <span data-ttu-id="d26a2-128">**IsLocal** 會指出裝載提供者所使用的 proxy 伺服器是否包含在商務用 Skype 伺服器拓撲中。</span><span class="sxs-lookup"><span data-stu-id="d26a2-128">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="d26a2-129">此參數必須設為 False。</span><span class="sxs-lookup"><span data-stu-id="d26a2-129">This parameter must be set to False.</span></span>

<span data-ttu-id="d26a2-130">例如，在商務用 Skype 管理命令介面中，下列 Cmdlet 會將雲端語音信箱設定為主控提供者：</span><span class="sxs-lookup"><span data-stu-id="d26a2-130">For example, in the Skype for Business Management shell, the following cmdlet configures Cloud Voicemail as the hosting provider:</span></span>


```PowerShell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a><span data-ttu-id="d26a2-131">設定主控語音信箱原則</span><span class="sxs-lookup"><span data-stu-id="d26a2-131">Configure a hosted voicemail policy</span></span>

<span data-ttu-id="d26a2-132">為了確保您組織的語音信箱路由傳送至雲端語音信箱服務，您必須為您的組織設定主控語音信箱原則。</span><span class="sxs-lookup"><span data-stu-id="d26a2-132">To ensure that voicemail for your organization is routed to the Cloud Voicemail service, you must configure a hosted voicemail policy for your organization.</span></span> <span data-ttu-id="d26a2-133">在許多情況下，只需要一個主控的語音信箱原則，您也可以修改全域原則，以符合您的所有需求。</span><span class="sxs-lookup"><span data-stu-id="d26a2-133">In many cases, only one hosted voicemail policy is required, and you can modify the global policy to meet all your needs.</span></span> <span data-ttu-id="d26a2-134">如果您的組織需要多個主控的語音信箱原則，您可以使用 cshostedvoicemailpolicy Cmdlet 新增原則。</span><span class="sxs-lookup"><span data-stu-id="d26a2-134">If your organization requires multiple hosted voicemail policies, you can add policies by using the new-cshostedvoicemailpolicy cmdlet.</span></span>

<span data-ttu-id="d26a2-135">若要修改全域原則，請在更新您的組織及 TenantID 後，在商務用 Skype Server 管理命令介面中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="d26a2-135">To modify the global policy, run the following command in the Skype for Business Server management shell after updating your Organization and TenantID:</span></span>

```PowerShell
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com
```

- <span data-ttu-id="d26a2-136">**Destination** 指定主控雲端語音信箱服務 (FQDN) 的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="d26a2-136">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Cloud Voicemail service.</span></span> <span data-ttu-id="d26a2-137">此值應設定為 **exap.um.outlook.com**。</span><span class="sxs-lookup"><span data-stu-id="d26a2-137">This value should be set to **exap.um.outlook.com**.</span></span>

- <span data-ttu-id="d26a2-138">**組織** 是指派給您租使用者的預設網域。</span><span class="sxs-lookup"><span data-stu-id="d26a2-138">**Organization** is the default domain assigned to your tenant.</span></span> <span data-ttu-id="d26a2-139">您可以讓租使用者管理員登入 office.com，按一下 [系統管理中心] app，然後流覽至左側的 [ **安裝** ]，然後按一下 [ **網域**]，以取得這項資訊。</span><span class="sxs-lookup"><span data-stu-id="d26a2-139">You can retrieve this information by having the tenant admin log in to office.com, click on the Admin Center app, navigate to **Setup** on the left, and click **Domains**.</span></span> <span data-ttu-id="d26a2-140">例如： mytenant.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="d26a2-140">For example: mytenant.onmicrosoft.com.</span></span>

    <span data-ttu-id="d26a2-141">組織名稱也是 Microsoft 365 或 Office 365 中的預設功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="d26a2-141">The Organization name is also the Default Domain name in Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="d26a2-142">若要確定已成功建立主控語音信箱原則，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="d26a2-142">To ensure that a hosted voicemail policy was created successfully, run the following command:</span></span>

```PowerShell
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a><span data-ttu-id="d26a2-143">指派主控的語音信箱原則</span><span class="sxs-lookup"><span data-stu-id="d26a2-143">Assign a hosted voicemail policy</span></span>

<span data-ttu-id="d26a2-144">根據預設，全域主控的語音信箱原則會指派給所有使用者。</span><span class="sxs-lookup"><span data-stu-id="d26a2-144">By default, the Global hosted voicemail policy is assigned to all users.</span></span> <span data-ttu-id="d26a2-145">如果您使用不同的原則，在為使用者啟用主控語音信箱之前，您必須先使用 [授與 CSHostedVoicemailPolicy 指令程式](/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) ，授與使用者所需的主控語音信箱原則。</span><span class="sxs-lookup"><span data-stu-id="d26a2-145">If you use a different policy, before enabling users for hosted voicemail, you must first grant users the desired hosted voicemail policy by using the [Grant-CSHostedVoicemailPolicy](/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) cmdlet.</span></span>

<span data-ttu-id="d26a2-146">例如，下列命令會將非全域主控語音信箱原則指派給使用者：</span><span class="sxs-lookup"><span data-stu-id="d26a2-146">For example, the following command assigns a non-Global hosted voicemail policy to a user:</span></span>


```PowerShell
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -PolicyName "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a><span data-ttu-id="d26a2-147">為使用者啟用雲端語音信箱</span><span class="sxs-lookup"><span data-stu-id="d26a2-147">Enable a user for Cloud Voicemail</span></span>

<span data-ttu-id="d26a2-148">若要讓使用者的語音信箱通話路由傳送至雲端語音信箱，您可以使用 [Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) Cmdlet 搭配 HostedVoiceMail 參數。</span><span class="sxs-lookup"><span data-stu-id="d26a2-148">To enable a user’s voicemail calls to be routed to Cloud Voicemail, you use the [Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) cmdlet with the HostedVoiceMail parameter.</span></span> 

<span data-ttu-id="d26a2-149">例如，下列命令會啟用雲端語音信箱的使用者帳戶：</span><span class="sxs-lookup"><span data-stu-id="d26a2-149">For example, the following command enables a user account for Cloud Voicemail:</span></span> 

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $True
```

<span data-ttu-id="d26a2-150">Cmdlet 會在全域、網站或使用者層級驗證雲端語音信箱原則--適用于此使用者。</span><span class="sxs-lookup"><span data-stu-id="d26a2-150">The cmdlet verifies that a Cloud Voicemail policy--at the global, site, or user level--applies to this user.</span></span> <span data-ttu-id="d26a2-151">若未套用原則，指令 Cmdlet 會失敗。</span><span class="sxs-lookup"><span data-stu-id="d26a2-151">If no policy applies, the cmdlet fails.</span></span>  

<span data-ttu-id="d26a2-152">下一個範例會停用雲端語音信箱的使用者帳戶：</span><span class="sxs-lookup"><span data-stu-id="d26a2-152">The next example disables a user account for Cloud Voicemail:</span></span>

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $False
```

<span data-ttu-id="d26a2-153">此 Cmdlet 會在全域、網站或使用者層級驗證沒有主控語音信箱原則--適用于此使用者。</span><span class="sxs-lookup"><span data-stu-id="d26a2-153">The cmdlet verifies that no hosted voicemail policy--at the global, site, or user level--applies to this user.</span></span> <span data-ttu-id="d26a2-154">若原則已套用，指令 Cmdlet 會失敗。</span><span class="sxs-lookup"><span data-stu-id="d26a2-154">If a policy does apply, the cmdlet fails.</span></span>

> [!NOTE]
>  <span data-ttu-id="d26a2-155">使用者必須已啟用 enterprise voice，才可使用 Microsoft 雲端語音信箱服務。</span><span class="sxs-lookup"><span data-stu-id="d26a2-155">Users must be enterprise-voice enabled to use the Microsoft Cloud Voicemail Service.</span></span>