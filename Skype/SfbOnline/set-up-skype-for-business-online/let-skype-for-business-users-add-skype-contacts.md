---
title: 讓商務用 Skype 使用者新增 Skype 連絡人
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 08666236-1894-42ae-8846-e49232bbc460
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
- LIL_Placement
description: '瞭解如何讓使用商務用 Skype 的使用者從貴組織外的商務用 skype 連絡人，然後將他們新增至他們的連絡人清單。 '
ms.openlocfilehash: 71282fe105c85cadca9aab341fc1b5e6ffbe47d2
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164472"
---
# <a name="let-skype-for-business-users-add-skype-contacts"></a><span data-ttu-id="a7bfa-103">讓商務用 Skype 使用者新增 Skype 連絡人</span><span class="sxs-lookup"><span data-stu-id="a7bfa-103">Let Skype for Business users add Skype contacts</span></span>

<span data-ttu-id="a7bfa-104">在商務用 Skype 中，您的使用者可以在使用 Skype （免費應用程式）的所有人搜尋和傳送即時消息！</span><span class="sxs-lookup"><span data-stu-id="a7bfa-104">With Skype for Business, your users can search for and IM with everyone who uses Skype, the free app!</span></span> <span data-ttu-id="a7bfa-105">本文說明您需要採取的動作，才能新增 Skype 連絡人。</span><span class="sxs-lookup"><span data-stu-id="a7bfa-105">This article explains what you need to do so they can add Skype contacts.</span></span> 
  
<span data-ttu-id="a7bfa-106">您必須在 Microsoft 365 或 Office 365 中擁有系統[管理員許可權](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US)，才能執行此動作。</span><span class="sxs-lookup"><span data-stu-id="a7bfa-106">You must have [admin permissions](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) in Microsoft 365 or Office 365 to do this.</span></span>

<span data-ttu-id="a7bfa-107">![商務用 Skype 標誌圖示](../images/sfb-logo-30x30.png) **使用商務用 Skype 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="a7bfa-107">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="a7bfa-108">使用您的 Microsoft 365 或 Office 365 系統管理員帳戶登[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage)入。</span><span class="sxs-lookup"><span data-stu-id="a7bfa-108">Sign in with your Microsoft 365 or Office 365 admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage).</span></span>
    
2. <span data-ttu-id="a7bfa-109">在系統管理中心中，移至 [系統**管理中心] 中心** > **商務用 Skype**。</span><span class="sxs-lookup"><span data-stu-id="a7bfa-109">In the admin center, go to **Admin Centers** > **Skype for Business**.</span></span> 
    
    ![選擇 [商務用 Skype 系統管理中心]。](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. <span data-ttu-id="a7bfa-111">在 [商務用 Skype 系統管理中心]\*\*\*\*，選擇 [組織]\*\*\*\*  >  [外部通訊]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a7bfa-111">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span> 
    
4. <span data-ttu-id="a7bfa-112">根據預設，您的使用者可以與使用商務用 Skype 的世界各地的其他人通訊（假設您的防火牆已設定為允許）。</span><span class="sxs-lookup"><span data-stu-id="a7bfa-112">By default, your users can communicate with all other people in the world who use Skype for Business (assuming your firewall has been configured to allow this).</span></span> 
    
    ![選擇 [讓人員使用商務用 Skype 與 Skype 通訊]。](../images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    <span data-ttu-id="a7bfa-114">如果您想要讓使用者與 Skype 使用者聊天，但不想讓他們與使用商務用 Skype 的其他人聊天，請選擇 [**僅針對允許的網域**]。</span><span class="sxs-lookup"><span data-stu-id="a7bfa-114">If you want your users to chat with Skype users, BUT you don't want them to chat with others who use Skype for Business, choose **On only for allowed domains**.</span></span> <span data-ttu-id="a7bfa-115">當您啟用與 Skype 使用者的聯絡時，系統會自動將 skype.com 新增為場景背後的允許網域。</span><span class="sxs-lookup"><span data-stu-id="a7bfa-115">When you enable contact with Skype users, skype.com is automatically added as an allowed domain behind the scenes.</span></span> 
    
    <span data-ttu-id="a7bfa-116">如果您想要允許世界各地的其他企業使用商務用 Skype 與其他公司的聯絡，請選擇 [**封鎖的網域除外**]，然後選擇**+** 新增這些網域。</span><span class="sxs-lookup"><span data-stu-id="a7bfa-116">If you want to allow contact from all other businesses in the world using Skype for Business, except specific ones, choose **On except for blocked domains**, and choose **+** to add those domains.</span></span> <span data-ttu-id="a7bfa-117">除了特定網域中的人員之外，所有人都能與您聯繫。</span><span class="sxs-lookup"><span data-stu-id="a7bfa-117">Everyone will be able to contact you except people on those specific domains.</span></span> <span data-ttu-id="a7bfa-118">（有些公司可能會選擇此選項，例如，如果他們在訴訟中，而且需要確保與其他業務不一樣。）</span><span class="sxs-lookup"><span data-stu-id="a7bfa-118">(Some businesses might choose this option, for example, if they are in litigation and need to ensure there's no contact with the other business.)</span></span>
    
5. <span data-ttu-id="a7bfa-119">選擇 [**讓人員使用商務用 Skype 與組織外部的 skype 使用者通訊**]。</span><span class="sxs-lookup"><span data-stu-id="a7bfa-119">Choose **Let people use Skype for Business to communicate with Skype users outside your organization**.</span></span> 
    
6.  <span data-ttu-id="a7bfa-120">如果您使用的是 Windows 防火牆，商務用 Skype 會自動開啟所需的埠。</span><span class="sxs-lookup"><span data-stu-id="a7bfa-120">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>
    
    <span data-ttu-id="a7bfa-121">如果您的組織使用另一個解決方案來限制您網路上的電腦連線至網際網路，請確定用戶端電腦能夠存取所有的[IP 位址和 url](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) ，瞭解 skype 連線與 Skype 目錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="a7bfa-121">If your organization uses another solution to restrict computers on your network from connecting to the Internet, ensure client computers are able to access all of the [IP addresses and URLs](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) for Skype connectivity and Skype Directory Search.</span></span> <span data-ttu-id="a7bfa-122">這可能需要將它們新增到防火牆或 proxy 基礎結構設定的輸出允許清單中。</span><span class="sxs-lookup"><span data-stu-id="a7bfa-122">This may require adding them to the outbound allow list in your firewall or proxy infrastructure configuration.</span></span>
    
7. <span data-ttu-id="a7bfa-123">請**等候長達24小時進行測試**。</span><span class="sxs-lookup"><span data-stu-id="a7bfa-123">**WAIT UP TO 24 HOURS TO TEST**.</span></span> <span data-ttu-id="a7bfa-124">每當您變更 [外部通訊] 設定時，最多可能需要24小時才能在所有資料中心上填入變更。</span><span class="sxs-lookup"><span data-stu-id="a7bfa-124">Any time you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>
    
8. <span data-ttu-id="a7bfa-125">向您的使用者顯示如何尋找 Skype 連絡人並將其新增至其商務用 Skype 連絡人清單中。</span><span class="sxs-lookup"><span data-stu-id="a7bfa-125">Show your users how to find and add Skype contacts to their list of Skype for Business contacts.</span></span> <span data-ttu-id="a7bfa-126">指出他們[在商務用 Skype 中搜尋人員](https://support.office.com/article/b12500ef-e37f-4d22-aade-c11277e53f19)。</span><span class="sxs-lookup"><span data-stu-id="a7bfa-126">Point them to [Search for people in Skype for Business](https://support.office.com/article/b12500ef-e37f-4d22-aade-c11277e53f19).</span></span>
    
## <a name="test-and-troubleshoot"></a><span data-ttu-id="a7bfa-127">測試和疑難排解</span><span class="sxs-lookup"><span data-stu-id="a7bfa-127">Test and troubleshoot</span></span>

<span data-ttu-id="a7bfa-128">若要測試您的設定，您需要位於不在公司防火牆後的 Skype 上的連絡人。</span><span class="sxs-lookup"><span data-stu-id="a7bfa-128">To test your setup, you need a contact on Skype who's not behind your company firewall.</span></span> <span data-ttu-id="a7bfa-129">他們可以使用 Gmail 帳戶、Outlook.com 帳戶或其他類型的電子郵件帳戶登入 Skype。</span><span class="sxs-lookup"><span data-stu-id="a7bfa-129">They can be signed in to Skype using a Gmail account, Outlook.com account, or other type of email account.</span></span>
  
1. <span data-ttu-id="a7bfa-130">在您變更 [外部通訊] 設定之後，請**等候長達24小時以進行測試**。</span><span class="sxs-lookup"><span data-stu-id="a7bfa-130">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>
    
2. <span data-ttu-id="a7bfa-131">登出商務用 Skype，然後再次登入，以查看搜尋 Skype 目錄的選項。</span><span class="sxs-lookup"><span data-stu-id="a7bfa-131">Sign out of Skype for Business and then sign in again so you see the option to search the Skype Directory.</span></span> 
    
    ![當 Skype 目錄醒目提示時，您可以搜尋擁有 Skype 帳戶的人員。](../images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
3. <span data-ttu-id="a7bfa-133">在商務用 Skype 中，搜尋您在 Skype 中的聯絡人，然後將要求傳送到聊天。</span><span class="sxs-lookup"><span data-stu-id="a7bfa-133">In Skype for Business, search for your contact in Skype, and send a request to chat.</span></span> 
    
    <span data-ttu-id="a7bfa-134">如果您收到由於公司原則而無法傳送的訊息，您必須仔細檢查您的[防火牆設定](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)。</span><span class="sxs-lookup"><span data-stu-id="a7bfa-134">If you get the message it couldn't be sent due to company policy, you need to double-check your [firewall settings](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span></span> 
    
4. <span data-ttu-id="a7bfa-135">測試問題是否是您的防火牆的另一種方法，就是移至不在防火牆背後的 wifi 位置（例如咖啡廳），並使用商務用 Skype 將要求傳送給您的 Skype 連絡人進行聊天。</span><span class="sxs-lookup"><span data-stu-id="a7bfa-135">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Skype for Business to send a request to your Skype contact to chat.</span></span> 
    
   - <span data-ttu-id="a7bfa-136">**如果您傳送給您的 Skype 聯絡人，且收件者沒有收到邀請**，請要求他們傳送聊天邀請。</span><span class="sxs-lookup"><span data-stu-id="a7bfa-136">**If you sent your Skype contact a request and they never received it**, ask them to send you a request to chat.</span></span> <span data-ttu-id="a7bfa-137">如果問題是在 Skype 與商務用 Skype 之間建立連線，通常就是解決問題。</span><span class="sxs-lookup"><span data-stu-id="a7bfa-137">If the problem was establishing a connection between Skype and Skype for Business, that often solves it.</span></span>
    
   - <span data-ttu-id="a7bfa-138">現在，如果郵件是在咖啡廳，而不是在您工作時，您知道問題是您的防火牆。</span><span class="sxs-lookup"><span data-stu-id="a7bfa-138">Now if the message goes through at the coffee shop but not when you're at work, then you know the problem is your firewall.</span></span> 
    
## <a name="what-you-can-and-cant-do"></a><span data-ttu-id="a7bfa-139">您可以或不能執行的動作</span><span class="sxs-lookup"><span data-stu-id="a7bfa-139">What you can and can't do</span></span>

- <span data-ttu-id="a7bfa-140">**Mac 版商務用 skype**無法搜尋及與 skype 連絡人進行通訊。</span><span class="sxs-lookup"><span data-stu-id="a7bfa-140">**Skype for Business on Mac** doesn't have the ability to search for and communicate with Skype contacts.</span></span>
    
- <span data-ttu-id="a7bfa-141">啟用 [目錄搜尋] 時，您可以搜尋並尋找 Skype 及商務用 Skype 使用者。</span><span class="sxs-lookup"><span data-stu-id="a7bfa-141">When directory search is enabled, you can search for and find Skype and Skype for Business users.</span></span> <span data-ttu-id="a7bfa-142">如果您由於某種原因無法搜尋目錄來找不到他們，您可以傳送連絡人要求，然後讓他們登入 Skype 並接受它，讓您可以與他們通訊。</span><span class="sxs-lookup"><span data-stu-id="a7bfa-142">If for some reason you can't find them by searching the directory, you can send them a contact request, and then have them sign in to Skype and accept it, so you can IM with them.</span></span> 
    
- <span data-ttu-id="a7bfa-143">無法允許與其他 IM 供應商（例如 Google 或 Facebook）的 IM 連線。</span><span class="sxs-lookup"><span data-stu-id="a7bfa-143">It's not possible to allow IM connectivity with other IM providers such as Google or Facebook.</span></span> <span data-ttu-id="a7bfa-144">您無法使用商務用 Skype 來傳送手機文字訊息。</span><span class="sxs-lookup"><span data-stu-id="a7bfa-144">You can't use Skype for Business to send cell phone text messages.</span></span>

- <span data-ttu-id="a7bfa-145">無法錄製 Skype 連絡人與商務用 Skype 連絡人之間的音訊或視頻通話。</span><span class="sxs-lookup"><span data-stu-id="a7bfa-145">It is not possible to record audio or video calls between a Skype Contact and Skype for Business contact.</span></span>
    
## <a name="what-features-are-available-when-adding-skype-contacts"></a><span data-ttu-id="a7bfa-146">新增 Skype 連絡人時可使用哪些功能？</span><span class="sxs-lookup"><span data-stu-id="a7bfa-146">What features are available when adding Skype contacts?</span></span>

<span data-ttu-id="a7bfa-147">以 Microsoft 帳戶（先前稱為 Windows Live ID）登入的 Skype 連絡人在與您的商務用 Skype 使用者交談時，可以取得部分（但並非全部）功能。</span><span class="sxs-lookup"><span data-stu-id="a7bfa-147">Skype contacts who signed in with their Microsoft account (formerly Windows Live ID) can get some, but not all, features when they are talking to your Skype for Business users.</span></span>
  
|<span data-ttu-id="a7bfa-148">**適用于 Skype 連絡人**</span><span class="sxs-lookup"><span data-stu-id="a7bfa-148">**Available with Skype contacts**</span></span>|<span data-ttu-id="a7bfa-149">**Skype 連絡人無法使用**</span><span class="sxs-lookup"><span data-stu-id="a7bfa-149">**Not available with Skype contacts**</span></span>|
|:-----|:-----|
| <span data-ttu-id="a7bfa-150">影片交談</span><span class="sxs-lookup"><span data-stu-id="a7bfa-150">Video conversations</span></span> <br/>  <span data-ttu-id="a7bfa-151">人員對人立即訊息</span><span class="sxs-lookup"><span data-stu-id="a7bfa-151">Person-to-person instant messaging</span></span> <br/>  <span data-ttu-id="a7bfa-152">目前狀態</span><span class="sxs-lookup"><span data-stu-id="a7bfa-152">Presence</span></span> <br/> | <span data-ttu-id="a7bfa-153">多方 IM 交談</span><span class="sxs-lookup"><span data-stu-id="a7bfa-153">Multi-party IM conversations</span></span> <br/>  <span data-ttu-id="a7bfa-154">三人以上的音訊與影片交談</span><span class="sxs-lookup"><span data-stu-id="a7bfa-154">Audio and video conversations with three or more people</span></span> <br/>  <span data-ttu-id="a7bfa-155">桌面與程式共用</span><span class="sxs-lookup"><span data-stu-id="a7bfa-155">Desktop and program sharing</span></span> <br/> |
   
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="a7bfa-156">相關主題</span><span class="sxs-lookup"><span data-stu-id="a7bfa-156">Related topics</span></span>

[<span data-ttu-id="a7bfa-157">允許使用者連絡外部商務用 Skype 使用者</span><span class="sxs-lookup"><span data-stu-id="a7bfa-157">Allow users to contact external Skype for Business users</span></span>](allow-users-to-contact-external-skype-for-business-users.md)
  
[<span data-ttu-id="a7bfa-158">設定商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="a7bfa-158">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

  
 
