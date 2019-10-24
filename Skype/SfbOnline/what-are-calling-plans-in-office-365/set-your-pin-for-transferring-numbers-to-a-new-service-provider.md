---
title: 設定您的 PIN 以將號碼轉移到新的服務提供者
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: f1defa5b-e49c-4d8c-a5f8-3f736201af5e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 若要從商務用 Skype Online 傳送或撥出電話號碼至其他電話服務提供者或承運人，您必須手動設定 PIN。 在您設定 PIN 之後，當您要求將電話號碼移植到外，您必須將它包含在 PIN 中。
ms.openlocfilehash: 7faad94822e6392d66c44dd67cb461abf69e47dd
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/28/2019
ms.locfileid: "37642297"
---
# <a name="set-your-pin-for-transferring-numbers-to-a-new-service-provider"></a><span data-ttu-id="1a893-104">設定您的 PIN 以將號碼轉移到新的服務提供者</span><span class="sxs-lookup"><span data-stu-id="1a893-104">Set your PIN for transferring numbers to a new service provider</span></span>

<span data-ttu-id="1a893-105">若要從商務用 Skype Online 傳送或撥*出*電話號碼至其他電話服務提供者或承運人，您必須手動設定 PIN。</span><span class="sxs-lookup"><span data-stu-id="1a893-105">To transfer or  *port out*  phone numbers from Skype for Business Online to another telephone service provider or carrier, you will need to manually set a PIN.</span></span> <span data-ttu-id="1a893-106">在您設定 PIN 之後，當您要求將電話號碼移植到外，您必須將它包含在 PIN 中。</span><span class="sxs-lookup"><span data-stu-id="1a893-106">After you set the PIN, you need to include it when you request to port a phone number out.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="1a893-107">埠輸出 PIN 只適用于美國的組織。</span><span class="sxs-lookup"><span data-stu-id="1a893-107">A port out PIN is only used for organizations in the United States.</span></span> 
  
<span data-ttu-id="1a893-108">請參閱[將電話號碼轉接至 Office 365](/microsoftteams/transfer-phone-numbers-to-office-365) ，以取得轉移和移植撥入/撥出電話號碼的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="1a893-108">See [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365) for more information about transferring and porting in/out phone numbers.</span></span>
  
<span data-ttu-id="1a893-109">以下是您應該知道的有關此 PIN 的一些特定資訊：</span><span class="sxs-lookup"><span data-stu-id="1a893-109">Here is some specific information about this PIN you should know:</span></span>
  
- <span data-ttu-id="1a893-110">如果未設定 PIN，您將無法從商務用 Skype Online 傳送或撥出電話號碼。</span><span class="sxs-lookup"><span data-stu-id="1a893-110">If a PIN isn't set, you won't be able to transfer or port out phone numbers from Skype for Business Online.</span></span>
    
- <span data-ttu-id="1a893-111">它可以包含6-10 位數（數位）。</span><span class="sxs-lookup"><span data-stu-id="1a893-111">It can contain 6-10 digits (numbers).</span></span>
    
- <span data-ttu-id="1a893-112">它不能包含字母或特殊字元。</span><span class="sxs-lookup"><span data-stu-id="1a893-112">It can't contain letters or special characters.</span></span>
    
- <span data-ttu-id="1a893-113">預設 PIN 是空白的，但如果您放入一個，就無法將它移除或設回空白。</span><span class="sxs-lookup"><span data-stu-id="1a893-113">The default PIN is blank, but if you put one in, you can't remove or set it back to blank.</span></span>
    
- <span data-ttu-id="1a893-114">您可以在加入 PIN 之後，更新或變更它。</span><span class="sxs-lookup"><span data-stu-id="1a893-114">You can update or change the PIN after you put one in.</span></span>
    
## <a name="set-up-your-pin"></a><span data-ttu-id="1a893-115">設定您的 PIN</span><span class="sxs-lookup"><span data-stu-id="1a893-115">Set up your PIN</span></span>

<span data-ttu-id="1a893-116">![](../images/sfb-logo-30x30.png) **使用商務用 skype 系統管理中心**顯示商務用 skype 標誌的圖示</span><span class="sxs-lookup"><span data-stu-id="1a893-116">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="1a893-117">使用您的公司或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="1a893-117">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="1a893-118">移至**Microsoft [團隊管理中心** > ] 的**舊版入口網站**。</span><span class="sxs-lookup"><span data-stu-id="1a893-118">Go to the **Microsoft Teams admin center** > **Legacy portal**.</span></span>
    
3. <span data-ttu-id="1a893-119">在左側導覽中，選擇 [**語音** > **埠順序**]。</span><span class="sxs-lookup"><span data-stu-id="1a893-119">In the left navigation, choose **Voice** > **Port orders**.</span></span>
    
4. <span data-ttu-id="1a893-120">按一下 [**設定]，然後管理**用於將號碼轉移或移植到其他服務運營商的 PIN。</span><span class="sxs-lookup"><span data-stu-id="1a893-120">Click **Set up and manage the PIN** that is used for transferring or porting numbers to another service carrier.</span></span>
    
5. <span data-ttu-id="1a893-121">在 [**設定或變更您的埠輸出 PIN**面板] 中，輸入您的 PIN，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="1a893-121">In the **Set or change your port out PIN** panel, enter your PIN and click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="1a893-122">如果您需要取得更多的電話號碼，請[聯絡商務產品支援-系統管理協助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span><span class="sxs-lookup"><span data-stu-id="1a893-122">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="1a893-123">相關主題</span><span class="sxs-lookup"><span data-stu-id="1a893-123">Related topics</span></span>
[<span data-ttu-id="1a893-124">傳送電話號碼常見問題</span><span class="sxs-lookup"><span data-stu-id="1a893-124">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="1a893-125">通話方案所用的不同類型的電話號碼</span><span class="sxs-lookup"><span data-stu-id="1a893-125">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="1a893-126">管理貴組織的電話號碼</span><span class="sxs-lookup"><span data-stu-id="1a893-126">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="1a893-127">緊急通話條款與條件</span><span class="sxs-lookup"><span data-stu-id="1a893-127">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="1a893-128">[商務用 Skype Online：緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="1a893-128">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
  

