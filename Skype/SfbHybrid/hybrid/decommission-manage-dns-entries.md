---
title: 在解除委任您的內部部署環境時管理 DNS 專案
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: 解除委任內部部署商務用 Skype 環境時，如何管理 DNS 專案的指示。
ms.openlocfilehash: bd8f3873ab28ef8e0b7ade86ffc95b4d5bb4e4cb
ms.sourcegitcommit: 405b22cfd94e50d651f4c3f73fb46780cd8a6d06
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458986"
---
# <a name="update-dns-entries-to-enable-your-organization-to-be-all-teams-only"></a><span data-ttu-id="300b2-103">更新 DNS 專案，讓您的組織全部 Teams</span><span class="sxs-lookup"><span data-stu-id="300b2-103">Update DNS entries to enable your organization to be all Teams Only</span></span>

<span data-ttu-id="300b2-104">先前部署商務用 Skype Server 或 Lync Server 的內部部署組織可能仍然具有指向內部部署商務用 Skype 部署的 DNS 專案。</span><span class="sxs-lookup"><span data-stu-id="300b2-104">Organizations that previously had on-premises deployments of Skype for Business Server or Lync Server may still have DNS entries that point to an on-premises Skype for Business deployment.</span></span> <span data-ttu-id="300b2-105">如果您的組織包括內部部署商務用 Skype 使用者，這些記錄就是必要的。</span><span class="sxs-lookup"><span data-stu-id="300b2-105">These records are required if your organization includes on-premises Skype for Business users.</span></span> <span data-ttu-id="300b2-106">不過，如果您的組織不再有任何內部部署商務用 Skype 或 Lync Server 使用者，這些記錄就不再是必要的。</span><span class="sxs-lookup"><span data-stu-id="300b2-106">However, once your organization no longer has any on-premises Skype for Business or Lync Server users, these records are no longer required.</span></span> <span data-ttu-id="300b2-107">實際上，在完成從內部部署至 Teams 的遷移時，必須更新這些記錄，使其指向 Microsoft 365 或移除。</span><span class="sxs-lookup"><span data-stu-id="300b2-107">And in fact, as part of completing the migration from on-premises to Teams, these records must be updated to point to Microsoft 365 or removed.</span></span> <span data-ttu-id="300b2-108">Microsoft 無法為您採取此步驟。</span><span class="sxs-lookup"><span data-stu-id="300b2-108">Microsoft cannot take this step for you.</span></span>

<span data-ttu-id="300b2-109">當您嘗試將 TeamsOnly 授與整個租使用者時，Teams 會檢查 DNS，判斷您的組織是否存在這些 dns 記錄中的任何記錄。</span><span class="sxs-lookup"><span data-stu-id="300b2-109">When attempting to grant TeamsOnly to the entire tenant, Teams will check DNS to determine if any of these DNS records exist for your organization.</span></span> <span data-ttu-id="300b2-110">如果找到任何記錄，且其指向 Microsoft 365 以外的專案，則嘗試將租使用者共存模式變更為 TeamsOnly 時，會因設計而失敗。</span><span class="sxs-lookup"><span data-stu-id="300b2-110">If any records are found, and if they point to something other than Microsoft 365, the attempt to change the tenant coexistence mode to TeamsOnly will fail by design.</span></span> <span data-ttu-id="300b2-111">這種設計是為了避免使用內部部署使用者的混合式組織誤將 TeamsOnly 模式套用到租使用者--因為這樣做會中斷任何內部部署商務用 Skype 使用者的同盟 (是否使用 Teams 或商務用 Skype) 。</span><span class="sxs-lookup"><span data-stu-id="300b2-111">This design is to prevent hybrid organizations with on-premises users from mistakenly applying TeamsOnly mode to the tenant--because doing so would break federation for any on-premises Skype for Business users (whether using Teams or Skype for Business).</span></span>

<span data-ttu-id="300b2-112">此外，這些記錄必須更新，讓您可以將 TeamsOnly 授與整個承租人。</span><span class="sxs-lookup"><span data-stu-id="300b2-112">Furthermore, these records must be updated so that you can grant TeamsOnly to the entire tenant.</span></span>

> [!Note] 
> <span data-ttu-id="300b2-113">在極少的情況下，將 DNS 設定為組織的內部部署與 Microsoft 365，可能會造成其他一些組織的同盟停止運作，直到其他組織更新其同盟設定為止：</span><span class="sxs-lookup"><span data-stu-id="300b2-113">In rare cases, changing DNS from pointing on premises to Microsoft 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span>
>
> - <span data-ttu-id="300b2-114">任何使用舊版直接同盟模型的同盟組織 (又稱為允許的夥伴伺服器) ，都必須更新其組織的允許網域專案，以移除 proxy FQDN。</span><span class="sxs-lookup"><span data-stu-id="300b2-114">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="300b2-115">這種舊版同盟模型不是以 DNS SRV 記錄為基礎，因此當您的組織移至雲端時，此設定將會到期。</span><span class="sxs-lookup"><span data-stu-id="300b2-115">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span>
> 
> - <span data-ttu-id="300b2-116">任何沒有啟用 sipfed <span> 之主機服務提供者的同盟組織。com 必須更新其設定，才能啟用該功能。</span><span class="sxs-lookup"><span data-stu-id="300b2-116">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="300b2-117">只有在同盟組織完全存在於內部部署，且決不會與任何混合式或線上租使用者同盟的情況下，才可能出現這種情況。</span><span class="sxs-lookup"><span data-stu-id="300b2-117">This situation is only possible if the federated organization is purely on-premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="300b2-118">在此情況下，與這些組織的同盟必須啟用其主機服務提供者後，才能運作。</span><span class="sxs-lookup"><span data-stu-id="300b2-118">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span>
>
> <span data-ttu-id="300b2-119">如果您懷疑任何同盟協力廠商可能使用的是直接同盟或尚未與任何線上或混合組織同盟，我們建議您在準備完成對雲端的遷移時，向他們傳送此資訊的通訊。</span><span class="sxs-lookup"><span data-stu-id="300b2-119">If you suspect that any of your federated partners may be using Direct Federation or have not federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>

## <a name="how-to-identify-stale-dns-records"></a><span data-ttu-id="300b2-120">如何識別陳舊的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="300b2-120">How to identify stale DNS records</span></span>

<span data-ttu-id="300b2-121">若要識別任何防止您的組織成為所有 Teams 的 DNS 記錄，您可以使用 Teams 系統管理中心，將共存模式變更為 TeamsOnly。</span><span class="sxs-lookup"><span data-stu-id="300b2-121">To identify any DNS records that prevent your organization from becoming all Teams Only, you can use the Teams admin center  to change the coexistence mode to TeamsOnly.</span></span> <span data-ttu-id="300b2-122">移至 **全組織設定**  ->  **Teams 升級**。</span><span class="sxs-lookup"><span data-stu-id="300b2-122">Go to **Org-wide setting** -> **Teams Upgrade**.</span></span> <span data-ttu-id="300b2-123">任何阻止組織成為 Teams 的 DNS 記錄，都將會包含在錯誤訊息中。</span><span class="sxs-lookup"><span data-stu-id="300b2-123">Any DNS records that prevent the organization from becoming Teams Only will be included in the error message.</span></span>  <span data-ttu-id="300b2-124">在事件中找不到 DNS 記錄時，您的組織的共存模式將變更為 TeamsOnly。</span><span class="sxs-lookup"><span data-stu-id="300b2-124">In the event no DNS records are found, the coexistence mode for your organization will be changed to TeamsOnly.</span></span> 

## <a name="how-to-remove-stale-dns-records"></a><span data-ttu-id="300b2-125">如何移除過時的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="300b2-125">How to remove stale DNS records</span></span>

<span data-ttu-id="300b2-126">如果您的組織已沒有任何內部部署商務用 Skype Server 或 Lync Server 使用者，您必須執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="300b2-126">If your organization no longer has any on-premises Skype for Business Server or Lync Server users, you must do the following:</span></span>

- <span data-ttu-id="300b2-127">更新商務用 Skype DNS 記錄，以指向 Microsoft 365 (而非內部部署) 。</span><span class="sxs-lookup"><span data-stu-id="300b2-127">Update Skype for Business DNS records to point to Microsoft 365 (instead of the on-premises deployment).</span></span>

- <span data-ttu-id="300b2-128">如果不再使用 SIP 網域，請移除商務用 Skype DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="300b2-128">Remove Skype for Business DNS records if the SIP domain is no longer used.</span></span> 

<span data-ttu-id="300b2-129">在每個可找到下列記錄的網域中，更新這些記錄，如下所示：</span><span class="sxs-lookup"><span data-stu-id="300b2-129">In each domain where you find any of the following records, update them as follows:</span></span>

| <span data-ttu-id="300b2-130">Record type (記錄類型)</span><span class="sxs-lookup"><span data-stu-id="300b2-130">Record type</span></span> | <span data-ttu-id="300b2-131">名稱</span><span class="sxs-lookup"><span data-stu-id="300b2-131">Name</span></span> | <span data-ttu-id="300b2-132">TTL</span><span class="sxs-lookup"><span data-stu-id="300b2-132">TTL</span></span> | <span data-ttu-id="300b2-133">Priority (優先順序)</span><span class="sxs-lookup"><span data-stu-id="300b2-133">Priority</span></span> | <span data-ttu-id="300b2-134">Weight (權數)</span><span class="sxs-lookup"><span data-stu-id="300b2-134">Weight</span></span> | <span data-ttu-id="300b2-135">Port (連接埠)</span><span class="sxs-lookup"><span data-stu-id="300b2-135">Port</span></span> | <span data-ttu-id="300b2-136">Value (值)</span><span class="sxs-lookup"><span data-stu-id="300b2-136">Value</span></span> |
| :-----| :-----| :---- | :-----| :-----| :-----| :-----|
| <span data-ttu-id="300b2-137">SRV</span><span class="sxs-lookup"><span data-stu-id="300b2-137">SRV</span></span> | <span data-ttu-id="300b2-138">_sipfederationtls tcp</span><span class="sxs-lookup"><span data-stu-id="300b2-138">_sipfederationtls.tcp</span></span> | <span data-ttu-id="300b2-139">3600</span><span class="sxs-lookup"><span data-stu-id="300b2-139">3600</span></span> |  <span data-ttu-id="300b2-140">100</span><span class="sxs-lookup"><span data-stu-id="300b2-140">100</span></span> | <span data-ttu-id="300b2-141">1 </span><span class="sxs-lookup"><span data-stu-id="300b2-141">1</span></span> | <span data-ttu-id="300b2-142">5061</span><span class="sxs-lookup"><span data-stu-id="300b2-142">5061</span></span>  | <span data-ttu-id="300b2-143">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="300b2-143">sipfed.online.lync.com</span></span> |
| <span data-ttu-id="300b2-144">SRV</span><span class="sxs-lookup"><span data-stu-id="300b2-144">SRV</span></span> | <span data-ttu-id="300b2-145">_sip tls</span><span class="sxs-lookup"><span data-stu-id="300b2-145">_sip.tls</span></span> | <span data-ttu-id="300b2-146">3600</span><span class="sxs-lookup"><span data-stu-id="300b2-146">3600</span></span>  | <span data-ttu-id="300b2-147">100</span><span class="sxs-lookup"><span data-stu-id="300b2-147">100</span></span> |    <span data-ttu-id="300b2-148">1 </span><span class="sxs-lookup"><span data-stu-id="300b2-148">1</span></span>   | <span data-ttu-id="300b2-149">443</span><span class="sxs-lookup"><span data-stu-id="300b2-149">443</span></span>   | <span data-ttu-id="300b2-150">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="300b2-150">sipdir.online.lync.com</span></span> |
| <span data-ttu-id="300b2-151">CNAME</span><span class="sxs-lookup"><span data-stu-id="300b2-151">CNAME</span></span> | <span data-ttu-id="300b2-152">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="300b2-152">lyncdiscover</span></span> |    <span data-ttu-id="300b2-153">3600</span><span class="sxs-lookup"><span data-stu-id="300b2-153">3600</span></span> |  <span data-ttu-id="300b2-154">不適用</span><span class="sxs-lookup"><span data-stu-id="300b2-154">N/A</span></span> |   <span data-ttu-id="300b2-155">不適用</span><span class="sxs-lookup"><span data-stu-id="300b2-155">N/A</span></span> |   <span data-ttu-id="300b2-156">不適用</span><span class="sxs-lookup"><span data-stu-id="300b2-156">N/A</span></span> |   <span data-ttu-id="300b2-157">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="300b2-157">webdir.online.lync.com</span></span> |
| <span data-ttu-id="300b2-158">CNAME</span><span class="sxs-lookup"><span data-stu-id="300b2-158">CNAME</span></span> |   <span data-ttu-id="300b2-159">sip</span><span class="sxs-lookup"><span data-stu-id="300b2-159">sip</span></span> | <span data-ttu-id="300b2-160">3600</span><span class="sxs-lookup"><span data-stu-id="300b2-160">3600</span></span> |    <span data-ttu-id="300b2-161">不適用</span><span class="sxs-lookup"><span data-stu-id="300b2-161">N/A</span></span> |   <span data-ttu-id="300b2-162">不適用</span><span class="sxs-lookup"><span data-stu-id="300b2-162">N/A</span></span>  | <span data-ttu-id="300b2-163">不適用</span><span class="sxs-lookup"><span data-stu-id="300b2-163">N/A</span></span> |    <span data-ttu-id="300b2-164">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="300b2-164">sipdir.online.lync.com</span></span> |
|||||||




