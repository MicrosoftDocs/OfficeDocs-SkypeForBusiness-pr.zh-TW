---
title: 設定 Microsoft Teams 會議室的帳戶
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
description: 請閱讀本主題以瞭解在 Exchange 和商務用 Skype 中為 Microsoft Teams 會議室進行帳戶的組組。
ms.openlocfilehash: 26879b2c07b859e65255ed84bedd4897b75d5caa
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117471"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a><span data-ttu-id="d6888-103">設定 Microsoft Teams 會議室的帳戶</span><span class="sxs-lookup"><span data-stu-id="d6888-103">Configure accounts for Microsoft Teams Rooms</span></span>
 
<span data-ttu-id="d6888-104">請閱讀本主題以瞭解 Microsoft Teams 會議室及其如何與 Exchange 和商務用 Skype 整合。</span><span class="sxs-lookup"><span data-stu-id="d6888-104">Read this topic to learn about Microsoft Teams Rooms and how it integrates with Exchange and Skype for Business.</span></span>
  
<span data-ttu-id="d6888-105">本主題將介紹如何在 Microsoft Exchange 和商務用 Skype 中建立 Microsoft Teams 會議室所使用的帳戶。</span><span class="sxs-lookup"><span data-stu-id="d6888-105">This topic introduces how to create accounts used by Microsoft Teams Rooms in Microsoft Exchange and Skype for Business.</span></span> <span data-ttu-id="d6888-106">Microsoft Teams 會議室裝置部署指示涵蓋在設定 [Microsoft Teams 會議室主控台中](console.md)。</span><span class="sxs-lookup"><span data-stu-id="d6888-106">Deployment instructions for Microsoft Teams Rooms devices is covered in [Configure a Microsoft Teams Rooms console](console.md).</span></span> <span data-ttu-id="d6888-107">您的基礎結構可能會屬於下列其中一種配置：</span><span class="sxs-lookup"><span data-stu-id="d6888-107">Your infrastructure will likely fall into one of the following configurations:</span></span>
  
- <span data-ttu-id="d6888-108">線上部署：貴組織的環境完全部署在 Microsoft 365 或 Office 365 上。</span><span class="sxs-lookup"><span data-stu-id="d6888-108">Online deployment: Your organization's environment is deployed entirely on Microsoft 365 or Office 365.</span></span> <span data-ttu-id="d6888-109">詳細資訊請參閱使用 [Microsoft 365 或 Office 365](with-office-365.md)部署 Microsoft Teams 會議室。</span><span class="sxs-lookup"><span data-stu-id="d6888-109">For more information, see [Deploy Microsoft Teams Rooms with Microsoft 365 or Office 365](with-office-365.md).</span></span>
    
- <span data-ttu-id="d6888-110">內部部署：貴組織有它所控制的伺服器，其中 Active Directory、Exchange 和商務用 Skype Server 是託管伺服器。</span><span class="sxs-lookup"><span data-stu-id="d6888-110">On-premises deployment: Your organization has servers that it controls, where Active Directory, Exchange, and Skype for Business Server are hosted.</span></span> <span data-ttu-id="d6888-111">詳細資訊，請參閱使用[商務用 Skype Server](with-skype-for-business-server-2015.md)部署 Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="d6888-111">For more information, see [Deploy Microsoft Teams Rooms with Skype for Business Server](with-skype-for-business-server-2015.md)</span></span>
    
- <span data-ttu-id="d6888-112">混合式部署：貴組織有混合式服務，有些是內部部署，有些則透過 Microsoft 365 或 Office 365 在線上託管。</span><span class="sxs-lookup"><span data-stu-id="d6888-112">Hybrid deployments: Your organization has a mix of services, with some hosted on premises and some hosted online through Microsoft 365 or Office 365.</span></span> <span data-ttu-id="d6888-113">Microsoft Teams 會議室支援下列混合式案例：</span><span class="sxs-lookup"><span data-stu-id="d6888-113">With Microsoft Teams Rooms, the following hybrid scenarios are supported:</span></span>
    
  - <span data-ttu-id="d6888-114">內部部署商務用 Skype Server 的 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="d6888-114">Exchange Online with Skype for Business Server on premises.</span></span> <span data-ttu-id="d6888-115">詳細資訊，請參閱使用[Exchange Online 部署 Microsoft Teams 會議室 (混合式) 。](with-exchange-online.md)</span><span class="sxs-lookup"><span data-stu-id="d6888-115">For more information, see [Deploy Microsoft Teams Rooms with Exchange Online (Hybrid)](with-exchange-online.md).</span></span>
    
  - <span data-ttu-id="d6888-116">使用 Microsoft Teams 或商務用 Skype Online 在內部部署中交換。</span><span class="sxs-lookup"><span data-stu-id="d6888-116">Exchange on premises with Microsoft Teams or Skype for Business Online.</span></span> <span data-ttu-id="d6888-117">詳細資訊，請參閱在內部部署 Exchange 部署[Microsoft Teams 會議室 (混合式) 。](with-exchange-on-premises.md)</span><span class="sxs-lookup"><span data-stu-id="d6888-117">For more information, see [Deploy Microsoft Teams Rooms with Exchange on premises (Hybrid)](with-exchange-on-premises.md).</span></span>
    
<span data-ttu-id="d6888-118">您擁有哪些設定將會影響您準備裝置設定時如何進行。</span><span class="sxs-lookup"><span data-stu-id="d6888-118">Which configuration you have will affect how you prepare for device setup.</span></span>
  
<span data-ttu-id="d6888-119">Microsoft Teams 會議室需要在 Active Directory、Exchange 和商務用 Skype 中指派「裝置帳戶」。</span><span class="sxs-lookup"><span data-stu-id="d6888-119">Microsoft Teams Rooms needs to be assigned a "device account" in Active Directory, Exchange, and Skype for Business.</span></span> <span data-ttu-id="d6888-120">該帳戶可用來存取其會議日曆並建立 Microsoft Teams 或商務用 Skype 的連接。</span><span class="sxs-lookup"><span data-stu-id="d6888-120">The account is used to access its meeting calendar and establish Microsoft Teams or Skype for Business connectivity.</span></span> <span data-ttu-id="d6888-121">人員可以預約此帳戶，並排程會議。</span><span class="sxs-lookup"><span data-stu-id="d6888-121">People can book this account by scheduling a meeting with it.</span></span> <span data-ttu-id="d6888-122">Microsoft Teams 會議室將能夠加入該會議，並提供各種功能給會議出席者。</span><span class="sxs-lookup"><span data-stu-id="d6888-122">Microsoft Teams Rooms will be able to join that meeting and provide various features to the meeting attendees.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d6888-123">沒有裝置帳戶，這些功能都不起作用。</span><span class="sxs-lookup"><span data-stu-id="d6888-123">Without a device account, none of these features will work.</span></span> 
  
<span data-ttu-id="d6888-124">每個裝置帳戶都是單一 Microsoft Teams 會議室裝置所特有的，而且需要一些設定：</span><span class="sxs-lookup"><span data-stu-id="d6888-124">Every device account is unique to a single Microsoft Teams Rooms device, and requires some setup:</span></span>
  
- <span data-ttu-id="d6888-125">裝置帳戶必須正確配置。</span><span class="sxs-lookup"><span data-stu-id="d6888-125">The device account must be configured correctly.</span></span>
    
- <span data-ttu-id="d6888-126">您的基礎結構必須配置為允許 Microsoft Teams 會議室驗證裝置帳戶，並取得適當的 Microsoft 服務。</span><span class="sxs-lookup"><span data-stu-id="d6888-126">Your infrastructure must be configured to allow Microsoft Teams Rooms to validate the device account, and to reach the appropriate Microsoft services.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="d6888-127">強烈建議在實際硬體安裝之前先完成帳戶建立。</span><span class="sxs-lookup"><span data-stu-id="d6888-127">It is highly recommended that account creation be done well in advance of actual hardware installation.</span></span> <span data-ttu-id="d6888-128">在理想情況下，帳戶準備是在安裝前兩到三周開始。</span><span class="sxs-lookup"><span data-stu-id="d6888-128">Ideally, account preparation is started two to three weeks before installation.</span></span> 

<span data-ttu-id="d6888-129">在混合式環境中，用於 Microsoft Teams 會議室的帳戶必須在 Azure Active Directory (AAD) 同步) 啟用密碼同步，因為 Microsoft Teams 會議室驗證需要 Microsoft 365 或 Office 365 驗證。</span><span class="sxs-lookup"><span data-stu-id="d6888-129">In hybrid environments the account used for Microsoft Teams Rooms must have password sync enabled in Azure Active Directory (AAD) Sync because Microsoft Teams Rooms authentication requires Microsoft 365 or Office 365 authentication.</span></span> <span data-ttu-id="d6888-130">設定帳戶時，請確認帳戶的 SIP 位址與 AAD 中的使用者主體名稱 (UPN) 一起。</span><span class="sxs-lookup"><span data-stu-id="d6888-130">When setting up the account, make sure that the account's SIP address matches its User Principal Name (UPN) in AAD.</span></span> 
  
<span data-ttu-id="d6888-131">您可以將裝置帳戶視為資源帳戶，而使用者可以將該帳戶視為會議室或會議空間的帳戶。</span><span class="sxs-lookup"><span data-stu-id="d6888-131">You can think of a device account as the resource account that people recognize as a conference room's or meeting space's account.</span></span> <span data-ttu-id="d6888-132">當您想要使用該會議室排程會議時，請邀請帳戶加入該會議。</span><span class="sxs-lookup"><span data-stu-id="d6888-132">When you want to schedule a meeting using that conference room, you invite the account to that meeting.</span></span> <span data-ttu-id="d6888-133">若要最有效地使用 Microsoft Teams 會議室，請對指派給每個會議室的裝置帳戶執行相同的操作。</span><span class="sxs-lookup"><span data-stu-id="d6888-133">In order to use Microsoft Teams Rooms most effectively, you do the same with the device account that's assigned to each one.</span></span>
  
<span data-ttu-id="d6888-134">如果您已經針對要安裝 Microsoft Teams 會議室的會議空間設定資源信箱帳戶，您可以將該資源帳戶變更為裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="d6888-134">If you already have a resource mailbox account set up for the meeting space where you're installing Microsoft Teams Rooms, you can change that resource account into a device account.</span></span> <span data-ttu-id="d6888-135">完成後，您只需要將裝置帳戶新增到 Microsoft Teams 會議室裝置。</span><span class="sxs-lookup"><span data-stu-id="d6888-135">Once that's done, all you need to do is add the device account to a Microsoft Teams Rooms device.</span></span> <span data-ttu-id="d6888-136">請參閱下方提供的裝置帳戶設定範例。</span><span class="sxs-lookup"><span data-stu-id="d6888-136">See device account setup examples provided below.</span></span>
  
<span data-ttu-id="d6888-137">使用其他組組時，您可以如規劃 Microsoft Teams 會議室管理與 Azure 監視器、使用[Azure](azure-monitor-deploy.md)監視器部署 Microsoft Teams 會議室管理，以及使用 Azure 監視器管理 Microsoft [Teams](azure-monitor-plan.md)會議室裝置中所述，使用 Microsoft Azure 監視器進行遠端[管理](azure-monitor-manage.md)。</span><span class="sxs-lookup"><span data-stu-id="d6888-137">With additional configuration, remote management is possible using Microsoft Azure Monitor as described in [Plan Microsoft Teams Rooms management with Azure Monitor](azure-monitor-plan.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md),  and [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor-manage.md).</span></span> 
  
## <a name="basic-configuration"></a><span data-ttu-id="d6888-138">基本組組</span><span class="sxs-lookup"><span data-stu-id="d6888-138">Basic configuration</span></span>

<span data-ttu-id="d6888-139">這些屬性代表裝置帳戶使用 Microsoft Teams 會議室的最低組組。</span><span class="sxs-lookup"><span data-stu-id="d6888-139">These properties represent the minimum configuration for a device account to work with Microsoft Teams Rooms.</span></span> <span data-ttu-id="d6888-140">您的裝置帳戶可能需要進一步設定。</span><span class="sxs-lookup"><span data-stu-id="d6888-140">Your device account may require further setup.</span></span>
  
|<span data-ttu-id="d6888-141">**屬性**</span><span class="sxs-lookup"><span data-stu-id="d6888-141">**Property**</span></span>|<span data-ttu-id="d6888-142">**目的**</span><span class="sxs-lookup"><span data-stu-id="d6888-142">**Purpose**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d6888-143">Exchange 信箱 (Exchange 2013 SP1 或更高版本，或 Exchange Online) </span><span class="sxs-lookup"><span data-stu-id="d6888-143">Exchange mailbox (Exchange 2013 SP1 or later, or Exchange Online)</span></span>  <br/> |<span data-ttu-id="d6888-144">使用 Exchange 信箱啟用帳戶，讓裝置帳戶能夠接收及傳送郵件和會議要求，以及顯示 Microsoft Teams 會議室裝置上的會議日曆。</span><span class="sxs-lookup"><span data-stu-id="d6888-144">Enabling the account with an Exchange mailbox gives the device account the capability to receive and send both mail and meeting requests, and to display a meetings calendar on the Microsoft Teams Rooms device.</span></span> <span data-ttu-id="d6888-145">Microsoft Teams 會議室信箱必須是會議室信箱。</span><span class="sxs-lookup"><span data-stu-id="d6888-145">The Microsoft Teams Rooms mailbox must be a room mailbox.</span></span>  <br/> |
|<span data-ttu-id="d6888-146">已啟用商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="d6888-146">Skype for Business is enabled</span></span>  <br/> |<span data-ttu-id="d6888-147">商務用 Skype 必須啟用，才能使用各種會議功能，例如視像通話、IM 和螢幕分享。</span><span class="sxs-lookup"><span data-stu-id="d6888-147">Skype for Business must be enabled in order to use various conferencing features, like video calls, IM, and screen-sharing.</span></span> <span data-ttu-id="d6888-148">同時支援商務用 Skype Online 和商務用 Skype Server。</span><span class="sxs-lookup"><span data-stu-id="d6888-148">Both Skype for Business Online and Skype for Business Server are supported.</span></span>  <br/> |
|<span data-ttu-id="d6888-149">啟用密碼</span><span class="sxs-lookup"><span data-stu-id="d6888-149">Password-enabled</span></span>  <br/> |<span data-ttu-id="d6888-150">裝置帳戶必須使用密碼啟用，或無法使用 Exchange 或商務用 Skype Server 進行驗證。</span><span class="sxs-lookup"><span data-stu-id="d6888-150">The device account must be enabled with a password, or it cannot authenticate with either Exchange or Skype for Business Server.</span></span>  <br/> |
   
## <a name="advanced-configuration"></a><span data-ttu-id="d6888-151">進位組</span><span class="sxs-lookup"><span data-stu-id="d6888-151">Advanced configuration</span></span>

<span data-ttu-id="d6888-152">雖然基本設定的屬性會允許在簡單的環境中設定裝置帳戶，但您的環境可能對於目錄帳戶有其他限制，Microsoft Teams 會議室才能順利使用裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="d6888-152">While the properties for the basic configuration will allow the device account to be set up in a simple environment, it is possible your environment has other restrictions on directory accounts that must be met in order for Microsoft Teams Rooms to successfully use the device account.</span></span>
  
|<span data-ttu-id="d6888-153">**屬性**</span><span class="sxs-lookup"><span data-stu-id="d6888-153">**Property**</span></span>|<span data-ttu-id="d6888-154">**目的**</span><span class="sxs-lookup"><span data-stu-id="d6888-154">**Purpose**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d6888-155">憑證式驗證</span><span class="sxs-lookup"><span data-stu-id="d6888-155">Certificate-based authentication</span></span>  <br/> |<span data-ttu-id="d6888-156">Exchange 和商務用 Skype Server 可能需要憑證。</span><span class="sxs-lookup"><span data-stu-id="d6888-156">Certificates may be required for both Exchange and Skype for Business Server.</span></span> <span data-ttu-id="d6888-157">若要部署憑證，您可以在以系統管理員登入時載入憑證。</span><span class="sxs-lookup"><span data-stu-id="d6888-157">To deploy certificates, you can load them when logged in as Admin.</span></span>  <br/> |
   
<span data-ttu-id="d6888-158">設定裝置帳戶最簡單的方法是使用遠端 Windows PowerShell 來設定它們。</span><span class="sxs-lookup"><span data-stu-id="d6888-158">The easiest way to set up device accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="d6888-159">Microsoft 提供 [SkypeRoomProvisioningScript.ps1， ](https://go.microsoft.com/fwlink/?linkid=870105)此腳本可協助建立新裝置帳戶，或驗證您現有的資源帳戶，以便協助您將這些帳戶轉換為相容的 Microsoft Teams 會議室裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="d6888-159">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new device accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms device accounts.</span></span>
  
<span data-ttu-id="d6888-160">如果您想要使用 Microsoft 365 或 Office 365 UI，而不想使用 Windows PowerShell Cmdlet，可以手動執行一些步驟。</span><span class="sxs-lookup"><span data-stu-id="d6888-160">If you prefer to use the Microsoft 365 or Office 365 UI over Windows PowerShell cmdlets, some steps can be performed manually.</span></span> <span data-ttu-id="d6888-161">請參閱 [使用 Microsoft 365 或 Office 365 建立裝置帳戶](/surface-hub/create-a-device-account-using-office-365)。</span><span class="sxs-lookup"><span data-stu-id="d6888-161">See [Creating a device account using Microsoft 365 or Office 365](/surface-hub/create-a-device-account-using-office-365).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d6888-162">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d6888-162">See also</span></span>

[<span data-ttu-id="d6888-163">規劃 Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="d6888-163">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="d6888-164">設定 Microsoft Teams 會議室主控台</span><span class="sxs-lookup"><span data-stu-id="d6888-164">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="d6888-165">管理 Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="d6888-165">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)