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
description: '瞭解如何讓商務用 Skype連絡人商務用 Skype組織外部的使用者，並新增到連絡人清單中。 '
ms.openlocfilehash: d68fc27dfb1c77935ce74e278092f6ed4ae3d7dc
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239832"
---
# <a name="let-skype-for-business-users-add-skype-contacts"></a><span data-ttu-id="8d21e-103">讓商務用 Skype 使用者新增 Skype 連絡人</span><span class="sxs-lookup"><span data-stu-id="8d21e-103">Let Skype for Business users add Skype contacts</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="8d21e-104">有了商務用 Skype，您的使用者可以與使用免費應用程式Skype搜尋和 IM！</span><span class="sxs-lookup"><span data-stu-id="8d21e-104">With Skype for Business, your users can search for and IM with everyone who uses Skype, the free app!</span></span> <span data-ttu-id="8d21e-105">本文將說明您需要執行哪些工作，以便他們新增Skype連絡人。</span><span class="sxs-lookup"><span data-stu-id="8d21e-105">This article explains what you need to do so they can add Skype contacts.</span></span> 
  
<span data-ttu-id="8d21e-106">您必須擁有[管理員許可權](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US)Microsoft 365或Office 365才能執行此操作。</span><span class="sxs-lookup"><span data-stu-id="8d21e-106">You must have [admin permissions](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) in Microsoft 365 or Office 365 to do this.</span></span>

<span data-ttu-id="8d21e-107">![商務用 Skype 標誌圖示](../images/sfb-logo-30x30.png) **使用商務用 Skype 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="8d21e-107">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="8d21e-108">使用您的帳戶Microsoft 365或Office 365系統管理員 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage) 帳戶。</span><span class="sxs-lookup"><span data-stu-id="8d21e-108">Sign in with your Microsoft 365 or Office 365 admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage).</span></span>
    
2. <span data-ttu-id="8d21e-109">在系統管理中心，前往 **系統管理中心**  >  **商務用 Skype。**</span><span class="sxs-lookup"><span data-stu-id="8d21e-109">In the admin center, go to **Admin Centers** > **Skype for Business**.</span></span> 
    
    ![選擇 商務用 Skype系統管理中心。](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. <span data-ttu-id="8d21e-111">在 [商務用 Skype 系統管理中心]，選擇 [組織]  >  [外部通訊]。</span><span class="sxs-lookup"><span data-stu-id="8d21e-111">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span> 
    
4. <span data-ttu-id="8d21e-112">根據預設，如果您的防火牆已商務用 Skype (允許此防火牆，您的使用者就可以與全世界所有使用此) 。</span><span class="sxs-lookup"><span data-stu-id="8d21e-112">By default, your users can communicate with all other people in the world who use Skype for Business (assuming your firewall has been configured to allow this).</span></span> 
    
    ![選擇讓人員使用商務用 Skype與Skype。](../images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    <span data-ttu-id="8d21e-114">如果您希望使用者與使用者Skype聊天，但您不希望他們與使用 商務用 Skype 的人聊天，請選擇僅適用于允許的 **網域**。</span><span class="sxs-lookup"><span data-stu-id="8d21e-114">If you want your users to chat with Skype users, BUT you don't want them to chat with others who use Skype for Business, choose **On only for allowed domains**.</span></span> <span data-ttu-id="8d21e-115">當您啟用與使用者Skype時，skype.com 會自動新增為幕後允許的網域。</span><span class="sxs-lookup"><span data-stu-id="8d21e-115">When you enable contact with Skype users, skype.com is automatically added as an allowed domain behind the scenes.</span></span> 
    
    <span data-ttu-id="8d21e-116">如果您想要允許來自全球所有其他企業使用 商務用 Skype，請選擇除了封鎖網域以外的 On，然後選擇新增 **+** 這些網域。</span><span class="sxs-lookup"><span data-stu-id="8d21e-116">If you want to allow contact from all other businesses in the world using Skype for Business, except specific ones, choose **On except for blocked domains**, and choose **+** to add those domains.</span></span> <span data-ttu-id="8d21e-117">除了這些特定網域上的人員之外，每個人都可以與您聯繫。</span><span class="sxs-lookup"><span data-stu-id="8d21e-117">Everyone will be able to contact you except people on those specific domains.</span></span> <span data-ttu-id="8d21e-118"> (某些企業可能會選擇這個選項，例如，如果他們正參與訴訟，而且需要確保沒有與其他企業聯繫。) </span><span class="sxs-lookup"><span data-stu-id="8d21e-118">(Some businesses might choose this option, for example, if they are in litigation and need to ensure there's no contact with the other business.)</span></span>
    
5. <span data-ttu-id="8d21e-119">選擇 **讓人員商務用 Skype組織Skype使用者通訊**。</span><span class="sxs-lookup"><span data-stu-id="8d21e-119">Choose **Let people use Skype for Business to communicate with Skype users outside your organization**.</span></span> 
    
6.  <span data-ttu-id="8d21e-120">如果您使用的是防火牆Windows，商務用 Skype自動開啟所需的埠。</span><span class="sxs-lookup"><span data-stu-id="8d21e-120">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>
    
    <span data-ttu-id="8d21e-121">如果貴組織使用另一個解決方案來限制網路上的電腦無法連接到網際網路，請確保用戶端電腦能夠存取 Skype 連接和目錄搜尋[](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)Skype IP 位址和 URL。</span><span class="sxs-lookup"><span data-stu-id="8d21e-121">If your organization uses another solution to restrict computers on your network from connecting to the Internet, ensure client computers are able to access all of the [IP addresses and URLs](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) for Skype connectivity and Skype Directory Search.</span></span> <span data-ttu-id="8d21e-122">這可能需要將它們新增到防火牆或 Proxy 基礎結構組配置的外發允許清單。</span><span class="sxs-lookup"><span data-stu-id="8d21e-122">This may require adding them to the outbound allow list in your firewall or proxy infrastructure configuration.</span></span>
    
7. <span data-ttu-id="8d21e-123">**等候最多 24 小時進行測試**。</span><span class="sxs-lookup"><span data-stu-id="8d21e-123">**WAIT UP TO 24 HOURS TO TEST**.</span></span> <span data-ttu-id="8d21e-124">每次變更外部通訊設定時，變更最多可能需要 24 小時，才能填入所有資料中心。</span><span class="sxs-lookup"><span data-stu-id="8d21e-124">Any time you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>
    
8. <span data-ttu-id="8d21e-125">向使用者顯示如何尋找連絡人，Skype連絡人的連絡人清單商務用 Skype連絡人。</span><span class="sxs-lookup"><span data-stu-id="8d21e-125">Show your users how to find and add Skype contacts to their list of Skype for Business contacts.</span></span> <span data-ttu-id="8d21e-126">指向 在 中[搜尋商務用 Skype。](https://support.office.com/article/b12500ef-e37f-4d22-aade-c11277e53f19)</span><span class="sxs-lookup"><span data-stu-id="8d21e-126">Point them to [Search for people in Skype for Business](https://support.office.com/article/b12500ef-e37f-4d22-aade-c11277e53f19).</span></span>
    
## <a name="test-and-troubleshoot"></a><span data-ttu-id="8d21e-127">測試和疑難排解</span><span class="sxs-lookup"><span data-stu-id="8d21e-127">Test and troubleshoot</span></span>

<span data-ttu-id="8d21e-128">若要測試您的設定，您需要在公司防火牆Skype的連絡人。</span><span class="sxs-lookup"><span data-stu-id="8d21e-128">To test your setup, you need a contact on Skype who's not behind your company firewall.</span></span> <span data-ttu-id="8d21e-129">他們可以使用 Gmail 帳戶、Outlook.com 帳戶或其他電子郵件帳戶Skype帳戶來登錄帳戶。</span><span class="sxs-lookup"><span data-stu-id="8d21e-129">They can be signed in to Skype using a Gmail account, Outlook.com account, or other type of email account.</span></span>
  
1. <span data-ttu-id="8d21e-130">變更外部通訊設定之後，請等候 **最多 24 小時進行測試**。</span><span class="sxs-lookup"><span data-stu-id="8d21e-130">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>
    
2. <span data-ttu-id="8d21e-131">登出帳戶商務用 Skype然後再次登錄，這樣您便看到搜尋目錄Skype選項。</span><span class="sxs-lookup"><span data-stu-id="8d21e-131">Sign out of Skype for Business and then sign in again so you see the option to search the Skype Directory.</span></span> 
    
    ![當Skype目錄時，您可以搜尋擁有帳戶Skype人員。](../images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
3. <span data-ttu-id="8d21e-133">在 商務用 Skype中，在 Skype中搜尋您的連絡人，然後傳送聊天要求。</span><span class="sxs-lookup"><span data-stu-id="8d21e-133">In Skype for Business, search for your contact in Skype, and send a request to chat.</span></span> 
    
    <span data-ttu-id="8d21e-134">如果您收到由於公司政策無法送出的郵件，您必須仔細檢查防火牆 [設定](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)。</span><span class="sxs-lookup"><span data-stu-id="8d21e-134">If you get the message it couldn't be sent due to company policy, you need to double-check your [firewall settings](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span></span> 
    
4. <span data-ttu-id="8d21e-135">另一個測試問題是否出在防火牆上的方法，是前往防火牆後面的 Wifi 位置，例如咖啡店，並使用 商務用 Skype 傳送要求給您的Skype聯絡人聊天。</span><span class="sxs-lookup"><span data-stu-id="8d21e-135">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Skype for Business to send a request to your Skype contact to chat.</span></span> 
    
   - <span data-ttu-id="8d21e-136">**如果您傳送您的Skype聯絡要求，但他們** 從未收到要求，請要求他們傳送聊天要求。</span><span class="sxs-lookup"><span data-stu-id="8d21e-136">**If you sent your Skype contact a request and they never received it**, ask them to send you a request to chat.</span></span> <span data-ttu-id="8d21e-137">如果問題在兩者之間建立Skype，商務用 Skype通常可以解決問題。</span><span class="sxs-lookup"><span data-stu-id="8d21e-137">If the problem was establishing a connection between Skype and Skype for Business, that often solves it.</span></span>
    
   - <span data-ttu-id="8d21e-138">現在，如果訊息在咖啡店傳遞，但您不在公司時，您就會知道問題出在防火牆上。</span><span class="sxs-lookup"><span data-stu-id="8d21e-138">Now if the message goes through at the coffee shop but not when you're at work, then you know the problem is your firewall.</span></span> 
    
## <a name="what-you-can-and-cant-do"></a><span data-ttu-id="8d21e-139">您可以和無法執行哪些工作</span><span class="sxs-lookup"><span data-stu-id="8d21e-139">What you can and can't do</span></span>

- <span data-ttu-id="8d21e-140">**商務用 Skype Mac** 上的連絡人無法搜尋並Skype連絡人。</span><span class="sxs-lookup"><span data-stu-id="8d21e-140">**Skype for Business on Mac** doesn't have the ability to search for and communicate with Skype contacts.</span></span>
    
- <span data-ttu-id="8d21e-141">啟用目錄搜尋時，您可以搜尋及尋找Skype商務用 Skype使用者。</span><span class="sxs-lookup"><span data-stu-id="8d21e-141">When directory search is enabled, you can search for and find Skype and Skype for Business users.</span></span> <span data-ttu-id="8d21e-142">如果您因為某種原因無法搜尋目錄來尋找，您可以傳送連絡人要求給他們，然後讓他們Skype並接受，好讓他們進行 IM。</span><span class="sxs-lookup"><span data-stu-id="8d21e-142">If for some reason you can't find them by searching the directory, you can send them a contact request, and then have them sign in to Skype and accept it, so you can IM with them.</span></span> 
    
- <span data-ttu-id="8d21e-143">無法允許與其他 IM 提供者 ，例如 Google 或 Facebook 的 IM 連接。</span><span class="sxs-lookup"><span data-stu-id="8d21e-143">It's not possible to allow IM connectivity with other IM providers such as Google or Facebook.</span></span> <span data-ttu-id="8d21e-144">您無法使用商務用 Skype手機文字訊息。</span><span class="sxs-lookup"><span data-stu-id="8d21e-144">You can't use Skype for Business to send cell phone text messages.</span></span>

- <span data-ttu-id="8d21e-145">無法錄製連絡人與連絡人Skype音訊商務用 Skype通話。</span><span class="sxs-lookup"><span data-stu-id="8d21e-145">It is not possible to record audio or video calls between a Skype Contact and Skype for Business contact.</span></span>
    
## <a name="what-features-are-available-when-adding-skype-contacts"></a><span data-ttu-id="8d21e-146">新增連絡人時，可以使用Skype功能？</span><span class="sxs-lookup"><span data-stu-id="8d21e-146">What features are available when adding Skype contacts?</span></span>

<span data-ttu-id="8d21e-147">Skype使用 Microsoft 帳戶 (前 Windows Live ID) 的連絡人在與您的使用者交談時，可以取得部分功能，但並非全部商務用 Skype功能。</span><span class="sxs-lookup"><span data-stu-id="8d21e-147">Skype contacts who signed in with their Microsoft account (formerly Windows Live ID) can get some, but not all, features when they are talking to your Skype for Business users.</span></span>
  
|<span data-ttu-id="8d21e-148">**適用于Skype連絡人**</span><span class="sxs-lookup"><span data-stu-id="8d21e-148">**Available with Skype contacts**</span></span>|<span data-ttu-id="8d21e-149">**無法與Skype一起使用**</span><span class="sxs-lookup"><span data-stu-id="8d21e-149">**Not available with Skype contacts**</span></span>|
|:-----|:-----|
| <span data-ttu-id="8d21e-150">視音訊交談</span><span class="sxs-lookup"><span data-stu-id="8d21e-150">Video conversations</span></span> <br/>  <span data-ttu-id="8d21e-151">人員對個人的立即訊息</span><span class="sxs-lookup"><span data-stu-id="8d21e-151">Person-to-person instant messaging</span></span> <br/>  <span data-ttu-id="8d21e-152">目前狀態</span><span class="sxs-lookup"><span data-stu-id="8d21e-152">Presence</span></span> <br/> | <span data-ttu-id="8d21e-153">多方 IM 交談</span><span class="sxs-lookup"><span data-stu-id="8d21e-153">Multi-party IM conversations</span></span> <br/>  <span data-ttu-id="8d21e-154">與三個或多個人員進行音訊和視音訊交談</span><span class="sxs-lookup"><span data-stu-id="8d21e-154">Audio and video conversations with three or more people</span></span> <br/>  <span data-ttu-id="8d21e-155">桌面與程式共用</span><span class="sxs-lookup"><span data-stu-id="8d21e-155">Desktop and program sharing</span></span> <br/> |
   
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="8d21e-156">相關主題</span><span class="sxs-lookup"><span data-stu-id="8d21e-156">Related topics</span></span>

[<span data-ttu-id="8d21e-157">允許使用者連絡外部商務用 Skype 使用者</span><span class="sxs-lookup"><span data-stu-id="8d21e-157">Allow users to contact external Skype for Business users</span></span>](allow-users-to-contact-external-skype-for-business-users.md)
  
[<span data-ttu-id="8d21e-158">設定商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="8d21e-158">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

  
 
