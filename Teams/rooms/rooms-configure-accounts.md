---
title: 設定帳戶Microsoft Teams 會議室
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
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: ''
description: 請閱讀本主題，瞭解如何在 Microsoft Teams 會議室 中Exchange商務用 Skype。
ms.openlocfilehash: 26879b2c07b859e65255ed84bedd4897b75d5caa
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117471"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a><span data-ttu-id="7589e-103">設定帳戶Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="7589e-103">Configure accounts for Microsoft Teams Rooms</span></span>
 
<span data-ttu-id="7589e-104">請閱讀本主題以瞭解Microsoft Teams 會議室，以及它如何與Exchange商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="7589e-104">Read this topic to learn about Microsoft Teams Rooms and how it integrates with Exchange and Skype for Business.</span></span>
  
<span data-ttu-id="7589e-105">本主題將介紹如何在 Microsoft Microsoft Teams 會議室 中建立Exchange帳戶商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="7589e-105">This topic introduces how to create accounts used by Microsoft Teams Rooms in Microsoft Exchange and Skype for Business.</span></span> <span data-ttu-id="7589e-106">設定主機Microsoft Teams 會議室裝置部署指示Microsoft Teams 會議室[說明](console.md)。</span><span class="sxs-lookup"><span data-stu-id="7589e-106">Deployment instructions for Microsoft Teams Rooms devices is covered in [Configure a Microsoft Teams Rooms console](console.md).</span></span> <span data-ttu-id="7589e-107">您的基礎結構可能會屬於下列其中一種配置：</span><span class="sxs-lookup"><span data-stu-id="7589e-107">Your infrastructure will likely fall into one of the following configurations:</span></span>
  
- <span data-ttu-id="7589e-108">線上部署：貴組織的環境完全部署在 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="7589e-108">Online deployment: Your organization's environment is deployed entirely on Microsoft 365 or Office 365.</span></span> <span data-ttu-id="7589e-109">詳細資訊，請參閱使用 Microsoft Teams 會議室[或 Microsoft 365 部署Office 365。](with-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="7589e-109">For more information, see [Deploy Microsoft Teams Rooms with Microsoft 365 or Office 365](with-office-365.md).</span></span>
    
- <span data-ttu-id="7589e-110">內部部署：貴組織有它所控制的伺服器，其中 Active Directory、Exchange和商務用 Skype Server是託管。</span><span class="sxs-lookup"><span data-stu-id="7589e-110">On-premises deployment: Your organization has servers that it controls, where Active Directory, Exchange, and Skype for Business Server are hosted.</span></span> <span data-ttu-id="7589e-111">詳細資訊，請參閱使用Microsoft Teams 會議室[部署商務用 Skype Server](with-skype-for-business-server-2015.md)</span><span class="sxs-lookup"><span data-stu-id="7589e-111">For more information, see [Deploy Microsoft Teams Rooms with Skype for Business Server](with-skype-for-business-server-2015.md)</span></span>
    
- <span data-ttu-id="7589e-112">混合式部署：貴組織有混合式服務，其中一些是內部部署，有些則透過Microsoft 365或Office 365。</span><span class="sxs-lookup"><span data-stu-id="7589e-112">Hybrid deployments: Your organization has a mix of services, with some hosted on premises and some hosted online through Microsoft 365 or Office 365.</span></span> <span data-ttu-id="7589e-113">使用 Microsoft Teams 會議室，支援下列混合式案例：</span><span class="sxs-lookup"><span data-stu-id="7589e-113">With Microsoft Teams Rooms, the following hybrid scenarios are supported:</span></span>
    
  - <span data-ttu-id="7589e-114">Exchange Online內部商務用 Skype Server中。</span><span class="sxs-lookup"><span data-stu-id="7589e-114">Exchange Online with Skype for Business Server on premises.</span></span> <span data-ttu-id="7589e-115">詳細資訊，請參閱使用混合[式Microsoft Teams 會議室部署Exchange Online () 。](with-exchange-online.md)</span><span class="sxs-lookup"><span data-stu-id="7589e-115">For more information, see [Deploy Microsoft Teams Rooms with Exchange Online (Hybrid)](with-exchange-online.md).</span></span>
    
  - <span data-ttu-id="7589e-116">Exchange內部部署使用 Microsoft Teams 或 商務用 Skype Online。</span><span class="sxs-lookup"><span data-stu-id="7589e-116">Exchange on premises with Microsoft Teams or Skype for Business Online.</span></span> <span data-ttu-id="7589e-117">詳細資訊，請參閱在內部部署[Microsoft Teams 會議室部署Exchange混合式 (部署) 。](with-exchange-on-premises.md)</span><span class="sxs-lookup"><span data-stu-id="7589e-117">For more information, see [Deploy Microsoft Teams Rooms with Exchange on premises (Hybrid)](with-exchange-on-premises.md).</span></span>
    
<span data-ttu-id="7589e-118">您擁有哪些設定將會影響您準備裝置設定時如何進行。</span><span class="sxs-lookup"><span data-stu-id="7589e-118">Which configuration you have will affect how you prepare for device setup.</span></span>
  
<span data-ttu-id="7589e-119">Microsoft Teams 會議室 Active Directory、Exchange和 商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="7589e-119">Microsoft Teams Rooms needs to be assigned a "device account" in Active Directory, Exchange, and Skype for Business.</span></span> <span data-ttu-id="7589e-120">該帳戶可用來存取其會議日曆，並建立Microsoft Teams或商務用 Skype連接。</span><span class="sxs-lookup"><span data-stu-id="7589e-120">The account is used to access its meeting calendar and establish Microsoft Teams or Skype for Business connectivity.</span></span> <span data-ttu-id="7589e-121">人員可以預約此帳戶，並排程會議。</span><span class="sxs-lookup"><span data-stu-id="7589e-121">People can book this account by scheduling a meeting with it.</span></span> <span data-ttu-id="7589e-122">Microsoft Teams 會議室加入會議，並提供各種功能給會議出席者。</span><span class="sxs-lookup"><span data-stu-id="7589e-122">Microsoft Teams Rooms will be able to join that meeting and provide various features to the meeting attendees.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7589e-123">沒有裝置帳戶，這些功能都不起作用。</span><span class="sxs-lookup"><span data-stu-id="7589e-123">Without a device account, none of these features will work.</span></span> 
  
<span data-ttu-id="7589e-124">每個裝置帳戶都是單一裝置Microsoft Teams 會議室唯一，而且需要一些設定：</span><span class="sxs-lookup"><span data-stu-id="7589e-124">Every device account is unique to a single Microsoft Teams Rooms device, and requires some setup:</span></span>
  
- <span data-ttu-id="7589e-125">裝置帳戶必須正確配置。</span><span class="sxs-lookup"><span data-stu-id="7589e-125">The device account must be configured correctly.</span></span>
    
- <span data-ttu-id="7589e-126">您的基礎結構必須配置為允許Microsoft Teams 會議室驗證裝置帳戶，並取得適當的Microsoft 服務。</span><span class="sxs-lookup"><span data-stu-id="7589e-126">Your infrastructure must be configured to allow Microsoft Teams Rooms to validate the device account, and to reach the appropriate Microsoft services.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="7589e-127">強烈建議在實際硬體安裝之前先完成帳戶建立。</span><span class="sxs-lookup"><span data-stu-id="7589e-127">It is highly recommended that account creation be done well in advance of actual hardware installation.</span></span> <span data-ttu-id="7589e-128">在理想情況下，帳戶準備是在安裝前兩到三周開始。</span><span class="sxs-lookup"><span data-stu-id="7589e-128">Ideally, account preparation is started two to three weeks before installation.</span></span> 

<span data-ttu-id="7589e-129">在混合式環境中，Microsoft Teams 會議室帳戶必須在 Azure Active Directory (AAD) 同步) 啟用密碼同步，因為 Microsoft Teams 會議室 驗證Microsoft 365或Office 365驗證。</span><span class="sxs-lookup"><span data-stu-id="7589e-129">In hybrid environments the account used for Microsoft Teams Rooms must have password sync enabled in Azure Active Directory (AAD) Sync because Microsoft Teams Rooms authentication requires Microsoft 365 or Office 365 authentication.</span></span> <span data-ttu-id="7589e-130">設定帳戶時，請確認帳戶的 SIP 位址與 AAD 中的使用者主體名稱 (UPN) 一起。</span><span class="sxs-lookup"><span data-stu-id="7589e-130">When setting up the account, make sure that the account's SIP address matches its User Principal Name (UPN) in AAD.</span></span> 
  
<span data-ttu-id="7589e-131">您可以將裝置帳戶視為資源帳戶，而使用者可以將該帳戶視為會議室或會議空間的帳戶。</span><span class="sxs-lookup"><span data-stu-id="7589e-131">You can think of a device account as the resource account that people recognize as a conference room's or meeting space's account.</span></span> <span data-ttu-id="7589e-132">當您想要使用該會議室排程會議時，請邀請帳戶加入該會議。</span><span class="sxs-lookup"><span data-stu-id="7589e-132">When you want to schedule a meeting using that conference room, you invite the account to that meeting.</span></span> <span data-ttu-id="7589e-133">若要最Microsoft Teams 會議室，請對指派給每個帳戶的裝置帳戶執行相同的操作。</span><span class="sxs-lookup"><span data-stu-id="7589e-133">In order to use Microsoft Teams Rooms most effectively, you do the same with the device account that's assigned to each one.</span></span>
  
<span data-ttu-id="7589e-134">如果您已經針對要安裝帳戶的會議空間設定資源信箱Microsoft Teams 會議室，您可以將該資源帳戶變更為裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="7589e-134">If you already have a resource mailbox account set up for the meeting space where you're installing Microsoft Teams Rooms, you can change that resource account into a device account.</span></span> <span data-ttu-id="7589e-135">完成之後，您只需要將裝置帳戶新增到Microsoft Teams 會議室裝置。</span><span class="sxs-lookup"><span data-stu-id="7589e-135">Once that's done, all you need to do is add the device account to a Microsoft Teams Rooms device.</span></span> <span data-ttu-id="7589e-136">請參閱下方提供的裝置帳戶設定範例。</span><span class="sxs-lookup"><span data-stu-id="7589e-136">See device account setup examples provided below.</span></span>
  
<span data-ttu-id="7589e-137">使用 Microsoft Azure其他組組時，您可以如規劃 Microsoft Teams 會議室 管理與[Azure 監視器](azure-monitor-plan.md)、使用 Azure 監視器部署[Microsoft Teams 會議室](azure-monitor-deploy.md)管理，以及使用 Azure 監視器管理 Microsoft Teams 會議室 裝置中所述，使用 Microsoft Teams 會議室 監視器進行遠端[管理](azure-monitor-manage.md)。</span><span class="sxs-lookup"><span data-stu-id="7589e-137">With additional configuration, remote management is possible using Microsoft Azure Monitor as described in [Plan Microsoft Teams Rooms management with Azure Monitor](azure-monitor-plan.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md),  and [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor-manage.md).</span></span> 
  
## <a name="basic-configuration"></a><span data-ttu-id="7589e-138">基本組組</span><span class="sxs-lookup"><span data-stu-id="7589e-138">Basic configuration</span></span>

<span data-ttu-id="7589e-139">這些屬性代表裝置帳戶使用Microsoft Teams 會議室。</span><span class="sxs-lookup"><span data-stu-id="7589e-139">These properties represent the minimum configuration for a device account to work with Microsoft Teams Rooms.</span></span> <span data-ttu-id="7589e-140">您的裝置帳戶可能需要進一步設定。</span><span class="sxs-lookup"><span data-stu-id="7589e-140">Your device account may require further setup.</span></span>
  
|<span data-ttu-id="7589e-141">**屬性**</span><span class="sxs-lookup"><span data-stu-id="7589e-141">**Property**</span></span>|<span data-ttu-id="7589e-142">**目的**</span><span class="sxs-lookup"><span data-stu-id="7589e-142">**Purpose**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7589e-143">Exchange 2013 SP1 (Exchange或稍後的信箱，或Exchange Online) </span><span class="sxs-lookup"><span data-stu-id="7589e-143">Exchange mailbox (Exchange 2013 SP1 or later, or Exchange Online)</span></span>  <br/> |<span data-ttu-id="7589e-144">啟用具有信箱Exchange帳戶，讓裝置帳戶能夠接收和傳送郵件和會議要求，以及顯示 Microsoft Teams 會議室 上的會議Microsoft Teams 會議室。</span><span class="sxs-lookup"><span data-stu-id="7589e-144">Enabling the account with an Exchange mailbox gives the device account the capability to receive and send both mail and meeting requests, and to display a meetings calendar on the Microsoft Teams Rooms device.</span></span> <span data-ttu-id="7589e-145">Microsoft Teams 會議室信箱必須是會議室信箱。</span><span class="sxs-lookup"><span data-stu-id="7589e-145">The Microsoft Teams Rooms mailbox must be a room mailbox.</span></span>  <br/> |
|<span data-ttu-id="7589e-146">商務用 Skype已啟用</span><span class="sxs-lookup"><span data-stu-id="7589e-146">Skype for Business is enabled</span></span>  <br/> |<span data-ttu-id="7589e-147">商務用 Skype，才能使用各種會議功能，例如視像通話、IM 和螢幕分享。</span><span class="sxs-lookup"><span data-stu-id="7589e-147">Skype for Business must be enabled in order to use various conferencing features, like video calls, IM, and screen-sharing.</span></span> <span data-ttu-id="7589e-148">同時商務用 Skype線上商務用 Skype Server支援。</span><span class="sxs-lookup"><span data-stu-id="7589e-148">Both Skype for Business Online and Skype for Business Server are supported.</span></span>  <br/> |
|<span data-ttu-id="7589e-149">啟用密碼</span><span class="sxs-lookup"><span data-stu-id="7589e-149">Password-enabled</span></span>  <br/> |<span data-ttu-id="7589e-150">裝置帳戶必須使用密碼啟用，否則無法使用 Exchange 或 商務用 Skype Server。</span><span class="sxs-lookup"><span data-stu-id="7589e-150">The device account must be enabled with a password, or it cannot authenticate with either Exchange or Skype for Business Server.</span></span>  <br/> |
   
## <a name="advanced-configuration"></a><span data-ttu-id="7589e-151">進位組</span><span class="sxs-lookup"><span data-stu-id="7589e-151">Advanced configuration</span></span>

<span data-ttu-id="7589e-152">雖然基本設定的屬性會允許裝置帳戶在簡單的環境中設定，但您的環境可能對於目錄帳戶有其他限制，Microsoft Teams 會議室 才能順利使用裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="7589e-152">While the properties for the basic configuration will allow the device account to be set up in a simple environment, it is possible your environment has other restrictions on directory accounts that must be met in order for Microsoft Teams Rooms to successfully use the device account.</span></span>
  
|<span data-ttu-id="7589e-153">**屬性**</span><span class="sxs-lookup"><span data-stu-id="7589e-153">**Property**</span></span>|<span data-ttu-id="7589e-154">**目的**</span><span class="sxs-lookup"><span data-stu-id="7589e-154">**Purpose**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7589e-155">憑證式驗證</span><span class="sxs-lookup"><span data-stu-id="7589e-155">Certificate-based authentication</span></span>  <br/> |<span data-ttu-id="7589e-156">系統可能需要憑證才能Exchange商務用 Skype Server。</span><span class="sxs-lookup"><span data-stu-id="7589e-156">Certificates may be required for both Exchange and Skype for Business Server.</span></span> <span data-ttu-id="7589e-157">若要部署憑證，您可以在以系統管理員登入時載入憑證。</span><span class="sxs-lookup"><span data-stu-id="7589e-157">To deploy certificates, you can load them when logged in as Admin.</span></span>  <br/> |
   
<span data-ttu-id="7589e-158">設定裝置帳戶最簡單的方法是使用遠端Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="7589e-158">The easiest way to set up device accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="7589e-159">Microsoft 提供[SkypeRoomProvisioningScript.ps1，](https://go.microsoft.com/fwlink/?linkid=870105)此腳本可協助建立新裝置帳戶，或驗證您現有的資源帳戶，以便協助您將這些帳戶轉換為Microsoft Teams 會議室帳戶。</span><span class="sxs-lookup"><span data-stu-id="7589e-159">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new device accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms device accounts.</span></span>
  
<span data-ttu-id="7589e-160">如果您想要在 Cmdlet Microsoft 365或Office 365 UI Windows PowerShell，可以手動執行一些步驟。</span><span class="sxs-lookup"><span data-stu-id="7589e-160">If you prefer to use the Microsoft 365 or Office 365 UI over Windows PowerShell cmdlets, some steps can be performed manually.</span></span> <span data-ttu-id="7589e-161">請參閱[使用 Microsoft 365 或 Office 365 建立Office 365。](/surface-hub/create-a-device-account-using-office-365)</span><span class="sxs-lookup"><span data-stu-id="7589e-161">See [Creating a device account using Microsoft 365 or Office 365](/surface-hub/create-a-device-account-using-office-365).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7589e-162">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7589e-162">See also</span></span>

[<span data-ttu-id="7589e-163">規劃 Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="7589e-163">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="7589e-164">設定 Microsoft Teams 會議室主控台</span><span class="sxs-lookup"><span data-stu-id="7589e-164">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="7589e-165">管理 Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="7589e-165">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)