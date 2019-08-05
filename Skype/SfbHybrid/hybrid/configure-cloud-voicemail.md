---
title: 針對內部部署使用者設定雲端語音信箱服務
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
ms.date: 2/11/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 針對駐留在商務用 Skype Server 上的使用者實施雲端語音信箱的指示。
ms.openlocfilehash: 99fc250ff4c01a0b51e784c165edb99cbb867b3c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36185467"
---
# <a name="configure-cloud-voicemail-service-for-on-premises-users"></a><span data-ttu-id="7f430-103">針對內部部署使用者設定雲端語音信箱服務</span><span class="sxs-lookup"><span data-stu-id="7f430-103">Configure Cloud Voicemail service for on-premises users</span></span>

## <a name="overview"></a><span data-ttu-id="7f430-104">概觀</span><span class="sxs-lookup"><span data-stu-id="7f430-104">Overview</span></span> 
<span data-ttu-id="7f430-105">本文說明如何針對商務用 Skype 內部部署使用者設定 Microsoft 雲端語音信箱服務。</span><span class="sxs-lookup"><span data-stu-id="7f430-105">This article describes how to configure Microsoft Cloud Voicemail service for your Skype for Business on-premises users.</span></span>  

<span data-ttu-id="7f430-106">本文假設您已在支援的拓撲中部署商務用 Skype Server, 且您已滿足設定混合式連線性的先決條件。</span><span class="sxs-lookup"><span data-stu-id="7f430-106">This article assumes that you already have Skype for Business Server deployed in a supported topology, and that you have met the prerequisites for setting up hybrid connectivity.</span></span>

<span data-ttu-id="7f430-107">如需有關實現雲端語音信箱的優點、規劃考慮及需求的詳細資訊, 請參閱[規劃雲端語音信箱服務](plan-cloud-voicemail.md)。</span><span class="sxs-lookup"><span data-stu-id="7f430-107">For more information about the benefits, planning considerations, and requirements for implementing Cloud Voicemail, see [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span></span>




<span data-ttu-id="7f430-108">設定雲端語音信箱涉及下列任務:</span><span class="sxs-lookup"><span data-stu-id="7f430-108">Configuring Cloud Voicemail involves the following tasks:</span></span>

1.  <span data-ttu-id="7f430-109">請確定您符合[規劃雲端語音信箱服務](plan-cloud-voicemail.md)中所述的先決條件。</span><span class="sxs-lookup"><span data-stu-id="7f430-109">Ensure that you have met the prerequisites as described in [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span></span>

2.  <span data-ttu-id="7f430-110">請確定您已按照[規劃混合式連線性](plan-hybrid-connectivity.md)和設定[混合式連接](configure-hybrid-connectivity.md)性中所述, 設定混合式連線性。</span><span class="sxs-lookup"><span data-stu-id="7f430-110">Ensure that you have set up hybrid connectivity as described in [Plan hybrid connectivity](plan-hybrid-connectivity.md) and [Configure hybrid connectivity](configure-hybrid-connectivity.md).</span></span> 

3.  <span data-ttu-id="7f430-111">在[Edge 伺服器上將雲端語音信箱設定為主機提供者](#configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server), 如本文所述。</span><span class="sxs-lookup"><span data-stu-id="7f430-111">[Configure Cloud Voicemail as the hosting provider on the Edge Server](#configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server) as described in this article.</span></span>

4.  <span data-ttu-id="7f430-112">如本文所述[設定託管語音信箱原則](#configure-a-hosted-voicemail-policy)。</span><span class="sxs-lookup"><span data-stu-id="7f430-112">[Configure a hosted voicemail policy](#configure-a-hosted-voicemail-policy) as described in this article.</span></span>

5.  <span data-ttu-id="7f430-113">如本文所述,[指派主持的語音信箱原則](#assign-a-hosted-voicemail-policy)。</span><span class="sxs-lookup"><span data-stu-id="7f430-113">[Assign a hosted voicemail policy](#assign-a-hosted-voicemail-policy) as described in this article.</span></span>

6.  <span data-ttu-id="7f430-114">如本文所述[, 啟用雲端語音信箱的使用者](#enable-a-user-for-cloud-voicemail)。</span><span class="sxs-lookup"><span data-stu-id="7f430-114">[Enable a user for Cloud Voicemail](#enable-a-user-for-cloud-voicemail) as described in this article.</span></span>


## <a name="configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server"></a><span data-ttu-id="7f430-115">在邊緣伺服器上將雲端語音信箱設定為主機提供者</span><span class="sxs-lookup"><span data-stu-id="7f430-115">Configure Cloud Voicemail as the hosting provider on the Edge Server</span></span> 

<span data-ttu-id="7f430-116">您可以透過使用 CsHostingProvider Cmdlet 與下列參數, 將雲端語音信箱設定為前端伺服器上的託管提供者:</span><span class="sxs-lookup"><span data-stu-id="7f430-116">You configure Cloud Voicemail as the hosting provider on a Front End Server by using the New-CsHostingProvider cmdlet with the following parameters:</span></span>

- <span data-ttu-id="7f430-117">身分**識別**會為您建立的主機服務提供者指定唯一的字串值識別碼;例如, 雲端語音信箱。</span><span class="sxs-lookup"><span data-stu-id="7f430-117">**Identity** specifies a unique string value identifier for the hosting provider that you are creating; for example, Cloud Voicemail.</span></span> 

- <span data-ttu-id="7f430-118">\*\*Enabled \*\* 指出網域與裝載提供者之間的網路連線是否已啟用。</span><span class="sxs-lookup"><span data-stu-id="7f430-118">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="7f430-119">此參數必須設定為 True。</span><span class="sxs-lookup"><span data-stu-id="7f430-119">This parameter must be set to True.</span></span>

- <span data-ttu-id="7f430-120">**EnabledSharedAddressSpace**表示主機服務提供者是否將用於共用的 SIP 位址空間案例中。</span><span class="sxs-lookup"><span data-stu-id="7f430-120">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="7f430-121">此參數必須設定為 True。</span><span class="sxs-lookup"><span data-stu-id="7f430-121">This parameter must be set to True.</span></span>

- <span data-ttu-id="7f430-122">**HostsOCSUsers**表示主機服務提供者是否是用來主持商務用 Skype Server 帳戶。</span><span class="sxs-lookup"><span data-stu-id="7f430-122">**HostsOCSUsers** indicates whether the hosting provider is used to host Skype for Business Server accounts.</span></span> <span data-ttu-id="7f430-123">此參數必須設為 False。</span><span class="sxs-lookup"><span data-stu-id="7f430-123">This parameter must be set to False.</span></span>

- <span data-ttu-id="7f430-124">**ProxyFQDN**指定主機提供者所使用之 proxy 伺服器的完整功能變數名稱 (FQDN);例如, proxyserver.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="7f430-124">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider; for example, proxyserver.contoso.com.</span></span> <span data-ttu-id="7f430-125">請與您的主機提供者聯繫以取得此資訊。</span><span class="sxs-lookup"><span data-stu-id="7f430-125">Contact your hosting provider for this information.</span></span> <span data-ttu-id="7f430-126">您無法修改此值。</span><span class="sxs-lookup"><span data-stu-id="7f430-126">This value cannot be modified.</span></span> <span data-ttu-id="7f430-127">如果主機服務提供者變更其 proxy 伺服器, 您將需要刪除該提供者的專案, 然後重新建立。</span><span class="sxs-lookup"><span data-stu-id="7f430-127">If the hosting provider changes its proxy server, you will need to delete and then re-create the entry for that provider.</span></span>

- <span data-ttu-id="7f430-128">**IsLocal**表示主機服務提供者所使用的 proxy 伺服器是否包含在您的商務用 Skype 伺服器拓撲中。</span><span class="sxs-lookup"><span data-stu-id="7f430-128">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="7f430-129">此參數必須設為 False。</span><span class="sxs-lookup"><span data-stu-id="7f430-129">This parameter must be set to False.</span></span>

<span data-ttu-id="7f430-130">例如, 在商務用 Skype 管理命令介面中, 下列 Cmdlet 會將雲端語音信箱配置為主機提供者:</span><span class="sxs-lookup"><span data-stu-id="7f430-130">For example, in the Skype for Business Management shell, the following cmdlet configures Cloud Voicemail as the hosting provider:</span></span>


```
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a><span data-ttu-id="7f430-131">設定託管語音信箱原則</span><span class="sxs-lookup"><span data-stu-id="7f430-131">Configure a hosted voicemail policy</span></span>

<span data-ttu-id="7f430-132">若要確保貴組織的語音信箱已傳送到雲端語音信箱服務, 您必須為貴組織設定託管的語音信箱原則。</span><span class="sxs-lookup"><span data-stu-id="7f430-132">To ensure that voicemail for your organization is routed to the Cloud Voicemail service, you must configure a hosted voicemail policy for your organization.</span></span> <span data-ttu-id="7f430-133">在許多情況下, 只需要一個主機語音信箱原則, 您可以修改全域原則來符合您的需求。</span><span class="sxs-lookup"><span data-stu-id="7f430-133">In many cases, only one hosted voicemail policy is required, and you can modify the global policy to meet all your needs.</span></span> <span data-ttu-id="7f430-134">如果您的組織需要多個託管的語音信箱原則, 您可以使用 cshostedvoicemailpolicy Cmdlet 新增原則。</span><span class="sxs-lookup"><span data-stu-id="7f430-134">If your organization requires multiple hosted voicemail policies, you can add policies by using the new-cshostedvoicemailpolicy cmdlet.</span></span>

<span data-ttu-id="7f430-135">若要修改全域原則, 請在更新貴組織和 TenantID 之後, 在商務用 Skype Server management shell 中執行下列命令:</span><span class="sxs-lookup"><span data-stu-id="7f430-135">To modify the global policy, run the following command in the Skype for Business Server management shell after updating your Organization and TenantID:</span></span>

```
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com -TenantID “11111111-1111-1111-1111-111111111111”
```

- <span data-ttu-id="7f430-136">**Destination**指定託管雲端語音信箱服務的完整功能變數名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="7f430-136">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Cloud Voicemail service.</span></span> <span data-ttu-id="7f430-137">此值應該設定為**exap.um.outlook.com**。</span><span class="sxs-lookup"><span data-stu-id="7f430-137">This value should be set to **exap.um.outlook.com**.</span></span>

- <span data-ttu-id="7f430-138">[**組織**] 是指派給您租使用者的預設網域。</span><span class="sxs-lookup"><span data-stu-id="7f430-138">**Organization** is the default domain assigned to your tenant.</span></span> <span data-ttu-id="7f430-139">您可以透過將租使用者管理員登入 office.com, 按一下 [系統管理中心] app, 流覽至左側的 [**設定**], 然後按一下 [**網域**] 來取得此資訊。</span><span class="sxs-lookup"><span data-stu-id="7f430-139">You can retrieve this information by having the tenant admin log in to office.com, click on the Admin Center app, navigate to **Setup** on the left, and click **Domains**.</span></span> <span data-ttu-id="7f430-140">例如: mytenant.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="7f430-140">For example: mytenant.onmicrosoft.com.</span></span>

    <span data-ttu-id="7f430-141">組織名稱也是 Office 365 中的預設功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="7f430-141">The Organization name is also the Default Domain name in Office 365.</span></span>

- <span data-ttu-id="7f430-142">**TenantID**是用來識別您在 Office 365 中的租使用者。</span><span class="sxs-lookup"><span data-stu-id="7f430-142">**TenantID** is used to identify your tenant in Office 365.</span></span> <span data-ttu-id="7f430-143">如需詳細資訊, 請參閱[尋找您的 Office 365 租使用者識別碼](https://support.office.com/en-us/article/find-your-office-365-tenant-id-6891b561-a52d-4ade-9f39-b492285e2c9b)。</span><span class="sxs-lookup"><span data-stu-id="7f430-143">For more information, see [Find your Office 365 tenant ID](https://support.office.com/en-us/article/find-your-office-365-tenant-id-6891b561-a52d-4ade-9f39-b492285e2c9b).</span></span>

<span data-ttu-id="7f430-144">若要確保已成功建立託管的語音信箱原則, 請執行下列命令:</span><span class="sxs-lookup"><span data-stu-id="7f430-144">To ensure that a hosted voicemail policy was created successfully, run the following command:</span></span>

```
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a><span data-ttu-id="7f430-145">指派託管的語音信箱原則</span><span class="sxs-lookup"><span data-stu-id="7f430-145">Assign a hosted voicemail policy</span></span>

<span data-ttu-id="7f430-146">根據預設, 全域託管的語音信箱原則會指派給所有使用者。</span><span class="sxs-lookup"><span data-stu-id="7f430-146">By default, the Global hosted voicemail policy is assigned to all users.</span></span> <span data-ttu-id="7f430-147">如果您使用不同的原則, 您必須先使用[Grant CSHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) Cmdlet, 將所需的託管語音信箱原則授與使用者。</span><span class="sxs-lookup"><span data-stu-id="7f430-147">If you use a different policy, before enabling users for hosted voicemail, you must first grant users the desired hosted voicemail policy by using the [Grant-CSHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) cmdlet.</span></span>

<span data-ttu-id="7f430-148">例如, 下列命令會將非全域託管的語音信箱原則指派給使用者:</span><span class="sxs-lookup"><span data-stu-id="7f430-148">For example, the following command assigns a non-Global hosted voicemail policy to a user:</span></span>


```
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -Identity "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a><span data-ttu-id="7f430-149">為使用者啟用雲端語音信箱</span><span class="sxs-lookup"><span data-stu-id="7f430-149">Enable a user for Cloud Voicemail</span></span>

<span data-ttu-id="7f430-150">若要讓使用者的語音信箱呼叫路由到雲端語音信箱, 您可以使用[move-csuser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) Cmdlet 與 HostedVoiceMail 參數。</span><span class="sxs-lookup"><span data-stu-id="7f430-150">To enable a user’s voicemail calls to be routed to Cloud Voicemail, you use the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) cmdlet with the HostedVoiceMail parameter.</span></span> 

<span data-ttu-id="7f430-151">例如, 下列命令可為雲端語音信箱啟用使用者帳戶:</span><span class="sxs-lookup"><span data-stu-id="7f430-151">For example, the following command enables a user account for Cloud Voicemail:</span></span> 

```Set-CsUser -Identity "User1" -HostedVoiceMail $True```

<span data-ttu-id="7f430-152">此 Cmdlet 會驗證雲端語音信箱原則--在全域、網站或使用者層級--適用于此使用者。</span><span class="sxs-lookup"><span data-stu-id="7f430-152">The cmdlet verifies that a Cloud Voicemail policy--at the global, site, or user level--applies to this user.</span></span> <span data-ttu-id="7f430-153">如果沒有套用任何原則, 則 Cmdlet 失敗。</span><span class="sxs-lookup"><span data-stu-id="7f430-153">If no policy applies, the cmdlet fails.</span></span>  

<span data-ttu-id="7f430-154">下一個範例會針對雲端語音信箱停用使用者帳戶:</span><span class="sxs-lookup"><span data-stu-id="7f430-154">The next example disables a user account for Cloud Voicemail:</span></span>

```Set-CsUser -Identity "User1" -HostedVoiceMail $False```

<span data-ttu-id="7f430-155">此 Cmdlet 會驗證任何託管的語音信箱原則 (在全域、網站或使用者層級) 適用于此使用者。</span><span class="sxs-lookup"><span data-stu-id="7f430-155">The cmdlet verifies that no hosted voicemail policy--at the global, site, or user level--applies to this user.</span></span> <span data-ttu-id="7f430-156">如果已套用原則, 則 Cmdlet 會失敗。</span><span class="sxs-lookup"><span data-stu-id="7f430-156">If a policy does apply, the cmdlet fails.</span></span>

> [!NOTE]
>  <span data-ttu-id="7f430-157">使用者必須是企業語音功能, 才能使用 Microsoft 雲端語音信箱服務。</span><span class="sxs-lookup"><span data-stu-id="7f430-157">Users must be enterprise-voice enabled to use the Microsoft Cloud Voicemail Service.</span></span>
