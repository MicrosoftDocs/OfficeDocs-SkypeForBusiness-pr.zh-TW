---
title: 設定 Microsoft 團隊聊天室的帳戶
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 5/10/2018
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: ''
description: 請閱讀本主題, 瞭解如何針對 Exchange 和商務用 Skype 中的 Microsoft 團隊聊天室設定帳戶。
ms.openlocfilehash: 30e887aa09b9013c3db18fb33133d11c639f9fe8
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243319"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a><span data-ttu-id="7020e-103">設定 Microsoft 團隊聊天室的帳戶</span><span class="sxs-lookup"><span data-stu-id="7020e-103">Configure accounts for Microsoft Teams Rooms</span></span>
 
<span data-ttu-id="7020e-104">請閱讀本主題以瞭解 Microsoft 團隊聊天室, 以及它如何與 Exchange 與商務用 Skype 整合。</span><span class="sxs-lookup"><span data-stu-id="7020e-104">Read this topic to learn about Microsoft Teams Rooms and how it integrates with Exchange and Skype for Business.</span></span>
  
<span data-ttu-id="7020e-105">本主題介紹如何在 Microsoft Exchange 和商務用 Skype 中建立 Microsoft 團隊聊天室所使用的帳戶。</span><span class="sxs-lookup"><span data-stu-id="7020e-105">This topic introduces how to create accounts used by Microsoft Teams Rooms in Microsoft Exchange and Skype for Business.</span></span> <span data-ttu-id="7020e-106">Microsoft 團隊聊天室裝置的部署指示將在 [[設定 Microsoft 團隊聊天室] 主控台](console.md)中講述。</span><span class="sxs-lookup"><span data-stu-id="7020e-106">Deployment instructions for Microsoft Teams Rooms devices is covered in [Configure a Microsoft Teams Rooms console](console.md).</span></span> <span data-ttu-id="7020e-107">您的基礎結構可能會分為下列其中一個設定:</span><span class="sxs-lookup"><span data-stu-id="7020e-107">Your infrastructure will likely fall into one of the following configurations:</span></span>
  
- <span data-ttu-id="7020e-108">線上部署: 貴組織的環境會完全部署在 Office 365 上。</span><span class="sxs-lookup"><span data-stu-id="7020e-108">Online deployment: Your organization's environment is deployed entirely on Office 365.</span></span> <span data-ttu-id="7020e-109">如需詳細資訊, 請參閱[使用 Office 365 部署 Microsoft 團隊聊天室](with-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="7020e-109">For more information, see [Deploy Microsoft Teams Rooms with Office 365](with-office-365.md).</span></span>
    
- <span data-ttu-id="7020e-110">內部部署: 您的組織擁有它所控制的伺服器, 其中包含 Active Directory、Exchange 及商務用 Skype Server 的主機。</span><span class="sxs-lookup"><span data-stu-id="7020e-110">On-premises deployment: Your organization has servers that it controls, where Active Directory, Exchange, and Skype for Business Server are hosted.</span></span> <span data-ttu-id="7020e-111">如需詳細資訊, 請參閱[使用商務用 Skype Server 部署 Microsoft 團隊聊天室](with-skype-for-business-server-2015.md)</span><span class="sxs-lookup"><span data-stu-id="7020e-111">For more information, see [Deploy Microsoft Teams Rooms with Skype for Business Server](with-skype-for-business-server-2015.md)</span></span>
    
- <span data-ttu-id="7020e-112">混合式部署: 您的組織有混合式的服務, 其中一些託管于內部部署, 以及一些透過 Office 365 託管的線上。</span><span class="sxs-lookup"><span data-stu-id="7020e-112">Hybrid deployments: Your organization has a mix of services, with some hosted on premises and some hosted online through Office 365.</span></span> <span data-ttu-id="7020e-113">使用 Microsoft 團隊聊天室時, 支援下列混合式案例:</span><span class="sxs-lookup"><span data-stu-id="7020e-113">With Microsoft Teams Rooms, the following hybrid scenarios are supported:</span></span> 
    
  - <span data-ttu-id="7020e-114">Exchange Online 與商務用 Skype Server 內部部署。</span><span class="sxs-lookup"><span data-stu-id="7020e-114">Exchange Online with Skype for Business Server on premises.</span></span> <span data-ttu-id="7020e-115">如需詳細資訊, 請參閱[使用 Exchange Online (混合式) 部署 Microsoft 團隊聊天室](with-exchange-online.md)。</span><span class="sxs-lookup"><span data-stu-id="7020e-115">For more information, see [Deploy Microsoft Teams Rooms with Exchange Online (Hybrid)](with-exchange-online.md).</span></span>
    
  - <span data-ttu-id="7020e-116">使用 Microsoft 團隊或商務用 Skype Online 在內部部署的 Exchange。</span><span class="sxs-lookup"><span data-stu-id="7020e-116">Exchange on premises with Microsoft Teams or Skype for Business Online.</span></span> <span data-ttu-id="7020e-117">如需詳細資訊, 請參閱[使用 Exchange 內部部署 (混合式) 部署 Microsoft 團隊聊天室](with-exchange-on-premises.md)。</span><span class="sxs-lookup"><span data-stu-id="7020e-117">For more information, see [Deploy Microsoft Teams Rooms with Exchange on premises (Hybrid)](with-exchange-on-premises.md).</span></span>
    
<span data-ttu-id="7020e-118">您所擁有的設定會影響您準備裝置設定的方式。</span><span class="sxs-lookup"><span data-stu-id="7020e-118">Which configuration you have will affect how you prepare for device setup.</span></span>
  
<span data-ttu-id="7020e-119">Microsoft 團隊聊天室需要在 Active Directory、Exchange 和商務用 Skype 中指派「裝置帳戶」。</span><span class="sxs-lookup"><span data-stu-id="7020e-119">Microsoft Teams Rooms needs to be assigned a "device account" in Active Directory, Exchange, and Skype for Business.</span></span> <span data-ttu-id="7020e-120">帳戶可用來存取其會議行事曆, 並建立 Microsoft 團隊或商務用 Skype 連線。</span><span class="sxs-lookup"><span data-stu-id="7020e-120">The account is used to access its meeting calendar and establish Microsoft Teams or Skype for Business connectivity.</span></span> <span data-ttu-id="7020e-121">使用者可以透過排程會議來預訂此帳戶。</span><span class="sxs-lookup"><span data-stu-id="7020e-121">People can book this account by scheduling a meeting with it.</span></span> <span data-ttu-id="7020e-122">Microsoft 團隊聊天室將能夠加入該會議, 並為會議出席者提供各種功能。</span><span class="sxs-lookup"><span data-stu-id="7020e-122">Microsoft Teams Rooms will be able to join that meeting and provide various features to the meeting attendees.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7020e-123">若沒有裝置帳戶, 這些功能都將無法運作。</span><span class="sxs-lookup"><span data-stu-id="7020e-123">Without a device account, none of these features will work.</span></span> 
  
<span data-ttu-id="7020e-124">每個裝置帳戶對於單一 Microsoft 團隊房間裝置而言都是唯一的, 需要進行一些設定:</span><span class="sxs-lookup"><span data-stu-id="7020e-124">Every device account is unique to a single Microsoft Teams Rooms device, and requires some setup:</span></span>
  
- <span data-ttu-id="7020e-125">裝置帳戶必須設定正確。</span><span class="sxs-lookup"><span data-stu-id="7020e-125">The device account must be configured correctly.</span></span>
    
- <span data-ttu-id="7020e-126">您的基礎結構必須設定為允許 Microsoft 團隊聊天室驗證裝置帳戶, 然後才能到達適當的 Microsoft 服務。</span><span class="sxs-lookup"><span data-stu-id="7020e-126">Your infrastructure must be configured to allow Microsoft Teams Rooms to validate the device account, and to reach the appropriate Microsoft services.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="7020e-127">強烈建議在實際的硬體安裝之前, 建立帳戶, 以進行良好的完成。</span><span class="sxs-lookup"><span data-stu-id="7020e-127">It is highly recommended that account creation be done well in advance of actual hardware installation.</span></span> <span data-ttu-id="7020e-128">理想的情況是, 帳戶準備必須在安裝前兩到三周內開始。</span><span class="sxs-lookup"><span data-stu-id="7020e-128">Ideally, account preparation is started two to three weeks before installation.</span></span> <span data-ttu-id="7020e-129">在混合式環境中, Microsoft 團隊聊天室所用的帳戶必須在 AAD 同步處理中啟用密碼同步處理, 因為 Microsoft 團隊會議室驗證需要 Office 365 驗證。</span><span class="sxs-lookup"><span data-stu-id="7020e-129">In hybrid environments the account used for Microsoft Teams Rooms must have password sync enabled in AAD Sync because Microsoft Teams Rooms authentication requires Office 365 authentication.</span></span>
  
<span data-ttu-id="7020e-130">您可以將裝置帳戶看作是人們辨識為會議室或會議空間帳戶的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="7020e-130">You can think of a device account as the resource account that people recognize as a conference room's or meeting space's account.</span></span> <span data-ttu-id="7020e-131">當您想要使用該會議室排程會議時, 您邀請該帳戶加入該會議。</span><span class="sxs-lookup"><span data-stu-id="7020e-131">When you want to schedule a meeting using that conference room, you invite the account to that meeting.</span></span> <span data-ttu-id="7020e-132">若要最有效地使用 Microsoft 團隊聊天室, 您可以對指派給它們的裝置帳戶執行相同的動作。</span><span class="sxs-lookup"><span data-stu-id="7020e-132">In order to use Microsoft Teams Rooms most effectively, you do the same with the device account that's assigned to each one.</span></span>
  
<span data-ttu-id="7020e-133">如果您已為安裝 Microsoft 團隊聊天室的會議空間設定資源信箱帳戶, 您可以將該資源帳戶變更為裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="7020e-133">If you already have a resource mailbox account set up for the meeting space where you're installing Microsoft Teams Rooms, you can change that resource account into a device account.</span></span> <span data-ttu-id="7020e-134">完成後, 您只需將裝置帳戶新增至 Microsoft 團隊聊天室裝置即可。</span><span class="sxs-lookup"><span data-stu-id="7020e-134">Once that's done, all you need to do is add the device account to a Microsoft Teams Rooms device.</span></span> <span data-ttu-id="7020e-135">請參閱下列提供的裝置帳戶設定範例。</span><span class="sxs-lookup"><span data-stu-id="7020e-135">See device account setup examples provided below.</span></span>
  
<span data-ttu-id="7020e-136">有了其他設定, 就可以使用 Microsoft Azure 監視器來[規劃 microsoft 的小組聊天室管理](azure-monitor-plan.md), 使用 azure 監視器來[部署 microsoft 團隊聊天室](azure-monitor-deploy.md)管理, 以及[使用 Azure 監視器管理 Microsoft 團隊聊天室裝置](azure-monitor-manage.md)。</span><span class="sxs-lookup"><span data-stu-id="7020e-136">With additional configuration, remote management is possible using Microsoft Azure Monitor as described in [Plan Microsoft Teams Rooms management with Azure Monitor](azure-monitor-plan.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md),  and [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor-manage.md).</span></span> 
  
## <a name="basic-configuration"></a><span data-ttu-id="7020e-137">基本設定</span><span class="sxs-lookup"><span data-stu-id="7020e-137">Basic configuration</span></span>

<span data-ttu-id="7020e-138">這些屬性代表與 Microsoft 團隊聊天室搭配使用之裝置帳戶的最小設定。</span><span class="sxs-lookup"><span data-stu-id="7020e-138">These properties represent the minimum configuration for a device account to work with Microsoft Teams Rooms.</span></span> <span data-ttu-id="7020e-139">您的裝置帳戶可能需要進一步設定。</span><span class="sxs-lookup"><span data-stu-id="7020e-139">Your device account may require further setup.</span></span>
  
|<span data-ttu-id="7020e-140">**Property**</span><span class="sxs-lookup"><span data-stu-id="7020e-140">**Property**</span></span>|<span data-ttu-id="7020e-141">**特殊**</span><span class="sxs-lookup"><span data-stu-id="7020e-141">**Purpose**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7020e-142">Exchange 信箱 (Exchange 2013 SP1 或更新版本, 或是 Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="7020e-142">Exchange mailbox (Exchange 2013 SP1 or later, or Exchange Online)</span></span>  <br/> |<span data-ttu-id="7020e-143">啟用具有 Exchange 信箱的帳戶可讓裝置帳戶能夠接收並傳送郵件和會議邀請, 以及在 Microsoft 團隊聊天室裝置上顯示會議行事曆。</span><span class="sxs-lookup"><span data-stu-id="7020e-143">Enabling the account with an Exchange mailbox gives the device account the capability to receive and send both mail and meeting requests, and to display a meetings calendar on the Microsoft Teams Rooms device.</span></span> <span data-ttu-id="7020e-144">Microsoft 團隊聊天室信箱必須是會議室信箱。</span><span class="sxs-lookup"><span data-stu-id="7020e-144">The Microsoft Teams Rooms mailbox must be a room mailbox.</span></span>  <br/> |
|<span data-ttu-id="7020e-145">已啟用商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="7020e-145">Skype for Business is enabled</span></span>  <br/> |<span data-ttu-id="7020e-146">必須啟用商務用 Skype, 才能使用各種會議功能, 例如, 影片通話、IM 和螢幕畫面分享。</span><span class="sxs-lookup"><span data-stu-id="7020e-146">Skype for Business must be enabled in order to use various conferencing features, like video calls, IM, and screen-sharing.</span></span> <span data-ttu-id="7020e-147">支援商務用 Skype Online 與商務用 Skype 伺服器。</span><span class="sxs-lookup"><span data-stu-id="7020e-147">Both Skype for Business Online and Skype for Business Server are supported.</span></span>  <br/> |
|<span data-ttu-id="7020e-148">已啟用密碼</span><span class="sxs-lookup"><span data-stu-id="7020e-148">Password-enabled</span></span>  <br/> |<span data-ttu-id="7020e-149">裝置帳戶必須以密碼啟用, 否則無法使用 Exchange 或商務用 Skype 伺服器進行驗證。</span><span class="sxs-lookup"><span data-stu-id="7020e-149">The device account must be enabled with a password, or it cannot authenticate with either Exchange or Skype for Business Server.</span></span>  <br/> |
   
## <a name="advanced-configuration"></a><span data-ttu-id="7020e-150">[高級設定]</span><span class="sxs-lookup"><span data-stu-id="7020e-150">Advanced configuration</span></span>

<span data-ttu-id="7020e-151">雖然基本設定的屬性可以讓裝置帳戶在簡單的環境中設定, 但您的環境可能對目錄帳戶有其他限制, 而您必須滿足這些帳戶, Microsoft 團隊聊天室才能成功使用[裝置帳戶]。</span><span class="sxs-lookup"><span data-stu-id="7020e-151">While the properties for the basic configuration will allow the device account to be set up in a simple environment, it is possible your environment has other restrictions on directory accounts that must be met in order for Microsoft Teams Rooms to successfully use the device account.</span></span>
  
|<span data-ttu-id="7020e-152">**Property**</span><span class="sxs-lookup"><span data-stu-id="7020e-152">**Property**</span></span>|<span data-ttu-id="7020e-153">**特殊**</span><span class="sxs-lookup"><span data-stu-id="7020e-153">**Purpose**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7020e-154">以憑證為基礎的驗證</span><span class="sxs-lookup"><span data-stu-id="7020e-154">Certificate-based authentication</span></span>  <br/> |<span data-ttu-id="7020e-155">Exchange 和商務用 Skype Server 都可能需要證書。</span><span class="sxs-lookup"><span data-stu-id="7020e-155">Certificates may be required for both Exchange and Skype for Business Server.</span></span> <span data-ttu-id="7020e-156">若要部署憑證, 您可以在以系統管理員身分登入時載入證書。</span><span class="sxs-lookup"><span data-stu-id="7020e-156">To deploy certificates, you can load them when logged in as Admin.</span></span>  <br/> |
   
<span data-ttu-id="7020e-157">設定裝置帳戶最簡單的方法, 就是使用遠端 Windows PowerShell 加以設定。</span><span class="sxs-lookup"><span data-stu-id="7020e-157">The easiest way to set up device accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="7020e-158">Microsoft 提供[SkypeRoomProvisioningScript. ps1](https://go.microsoft.com/fwlink/?linkid=870105), 此腳本將協助您建立新的裝置帳戶, 或驗證現有的資源帳戶, 以協助您將它們轉換成相容的 Microsoft 團隊聊天室裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="7020e-158">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new device accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms device accounts.</span></span>
  
<span data-ttu-id="7020e-159">如果您想要在 Windows PowerShell Cmdlet 上使用 Office 365 UI, 可以手動執行一些步驟。</span><span class="sxs-lookup"><span data-stu-id="7020e-159">If you prefer to use the Office 365 UI over Windows PowerShell cmdlets, some steps can be performed manually.</span></span> <span data-ttu-id="7020e-160">請參閱[使用 Office 365 建立裝置帳戶](https://docs.microsoft.com/surface-hub/create-a-device-account-using-office-365)。</span><span class="sxs-lookup"><span data-stu-id="7020e-160">See [Creating a device account using Office 365](https://docs.microsoft.com/surface-hub/create-a-device-account-using-office-365).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7020e-161">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7020e-161">See also</span></span>

[<span data-ttu-id="7020e-162">規劃 Microsoft 團隊聊天室</span><span class="sxs-lookup"><span data-stu-id="7020e-162">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)
  
[<span data-ttu-id="7020e-163">設定 Microsoft 團隊聊天室主控台</span><span class="sxs-lookup"><span data-stu-id="7020e-163">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="7020e-164">管理 Microsoft 團隊聊天室</span><span class="sxs-lookup"><span data-stu-id="7020e-164">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)

