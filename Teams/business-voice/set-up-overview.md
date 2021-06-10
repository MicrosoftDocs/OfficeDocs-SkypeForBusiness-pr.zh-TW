---
title: 設定Microsoft 365 商務語音
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: 瞭解如何在中小型企業或Microsoft 365 商務語音中設定目標。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 892b093003accf782b7fb6c0a6234bf1f8beb952
ms.sourcegitcommit: 592e5a0638c7739dfaa3565b67d4edc621eebc9f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/26/2021
ms.locfileid: "52656036"
---
# <a name="set-up-microsoft-365-business-voice"></a><span data-ttu-id="34c55-103">設定Microsoft 365 商務語音</span><span class="sxs-lookup"><span data-stu-id="34c55-103">Set up Microsoft 365 Business Voice</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWEu8R]  

</br>

<span data-ttu-id="34c55-104">Business Voice 是一套完整的電話系統，可取代現有的電話提供者。</span><span class="sxs-lookup"><span data-stu-id="34c55-104">Business Voice is a complete phone system that can replace your existing telephony provider.</span></span> <span data-ttu-id="34c55-105">無論您是第一次設定電話號碼的新企業，或是從舊版內部部署電話提供者移走的已建立企業，這些文章中的步驟都可以説明您使用 Business Voice 快速上手。</span><span class="sxs-lookup"><span data-stu-id="34c55-105">Whether you're a new business setting up phone numbers for the first time, or an established business moving from a legacy on-premises telephony provider, the steps in these articles can help you get up and running with Business Voice.</span></span> <span data-ttu-id="34c55-106">當您完成設定 Business Voice 時：</span><span class="sxs-lookup"><span data-stu-id="34c55-106">When you're finished setting up Business Voice:</span></span>

* <span data-ttu-id="34c55-107">您可以在主要公司電話線路上接聽付費或免付費電話。</span><span class="sxs-lookup"><span data-stu-id="34c55-107">You'll be able to receive toll or toll-free phone calls on a main company phone line.</span></span> <span data-ttu-id="34c55-108">您甚至可以設定通話功能表。</span><span class="sxs-lookup"><span data-stu-id="34c55-108">You can even set up a call menu if you want.</span></span>
* <span data-ttu-id="34c55-109">使用 Business Voice 設定的使用者會擁有自己的直接撥號電話號碼，他們可以使用該號碼從任何已安裝電話的裝置撥打Teams電話。</span><span class="sxs-lookup"><span data-stu-id="34c55-109">Users set up with Business Voice will have their own direct-dial phone numbers that they can use to make and receive phone calls from any device with Teams installed.</span></span>
* <span data-ttu-id="34c55-110">如果會議參與者無法從用戶端加入會議，就可以使用一般電話Teams會議。</span><span class="sxs-lookup"><span data-stu-id="34c55-110">Meeting participants will be able to call in to meetings using a regular phone if they're unable to join from a Teams client.</span></span>
* <span data-ttu-id="34c55-111">如果您有現有的電話號碼，在移至 Business Voice 之後，就可以繼續使用。</span><span class="sxs-lookup"><span data-stu-id="34c55-111">If you have existing phone numbers, you'll be able to continue using them after they're moved to Business Voice.</span></span>

<span data-ttu-id="34c55-112">如果您想要深入瞭解商務語音，請查看什麼是[Microsoft 365 商務語音？](whats-business-voice.md)。</span><span class="sxs-lookup"><span data-stu-id="34c55-112">If you want to learn more about Business Voice, check out [What is Microsoft 365 Business Voice?](whats-business-voice.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="34c55-113">這些文章中的資訊僅適用于商務語音 **與通話** 方案。</span><span class="sxs-lookup"><span data-stu-id="34c55-113">The information in these articles is applicable to Business Voice **with** Calling Plan only.</span></span> <span data-ttu-id="34c55-114">含通話方案的商務語音只有在選取的國家和地區才能使用。</span><span class="sxs-lookup"><span data-stu-id="34c55-114">Business Voice with Calling Plan is available only in select countries and regions.</span></span> <span data-ttu-id="34c55-115">開始設定商務語音之前，請檢查商務語音[](country-region-availability.md)的國/地區可用性，查看您的國家/地區是否支援商務語音與通話方案。</span><span class="sxs-lookup"><span data-stu-id="34c55-115">Before you start setting up Business Voice, check [Country and region availability for Business Voice](country-region-availability.md) to see whether your country or region supports Business Voice with Calling Plan.</span></span>
>
> <span data-ttu-id="34c55-116">如果您的租用戶所在國家或地區不支援含通話方案的商務語音，請參閱[從 Microsoft 轉銷商或合作夥伴取得協助](reseller-partner-support.md)。</span><span class="sxs-lookup"><span data-stu-id="34c55-116">If your tenant is located in a country or region that doesn't support Business Voice with Calling Plan, check out [Get help from a Microsoft reseller or partner](reseller-partner-support.md).</span></span>
>
> <span data-ttu-id="34c55-117">只有當您的使用者信箱位於 Microsoft 365 中時，才能使用 Microsoft Teams 和商務語音。</span><span class="sxs-lookup"><span data-stu-id="34c55-117">Microsoft Teams and Business Voice only work when your users' mailboxes are located in Microsoft 365.</span></span>  <span data-ttu-id="34c55-118">不支援內部部署 Exchange Server 上的信箱。</span><span class="sxs-lookup"><span data-stu-id="34c55-118">They don't support mailboxes on on-premises Exchange Server.</span></span>
>
> <span data-ttu-id="34c55-119">此設定程式不支援商務用 Skype部署。</span><span class="sxs-lookup"><span data-stu-id="34c55-119">This setup process doesn't support Skype for Business hybrid deployments.</span></span> <span data-ttu-id="34c55-120">如果您擁有商務用 Skype 混合式部署，且想要設定 Business Voice，請參閱[在組織中設定電話系統](../setting-up-your-phone-system.md)。</span><span class="sxs-lookup"><span data-stu-id="34c55-120">If you have a Skype for Business hybrid deployment and want to set up Business Voice, check out [Set up Phone System in your organization](../setting-up-your-phone-system.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="34c55-121">開始之前</span><span class="sxs-lookup"><span data-stu-id="34c55-121">Before you begin</span></span>

<span data-ttu-id="34c55-122">在設定商務語音之前，您需要執行一些操作。</span><span class="sxs-lookup"><span data-stu-id="34c55-122">Before you set up Business Voice, there are a few things you need to do.</span></span> <span data-ttu-id="34c55-123">下列工作會確保貴組織已準備好使用商務語音。</span><span class="sxs-lookup"><span data-stu-id="34c55-123">The following tasks will make sure your organization is ready for Business Voice.</span></span>

* <span data-ttu-id="34c55-124">**購買商務語音授權** ，如果您想要取得免付費號碼或撥打長途電話，請購買通訊信用額度。</span><span class="sxs-lookup"><span data-stu-id="34c55-124">**Buy Business Voice licenses** and, if you want to get a toll-free number or make long-distance phone calls, Communication Credits.</span></span> <span data-ttu-id="34c55-125">若要詳細資訊，請參閱我需要購買哪些產品，以[使用Microsoft 365 商務語音？](what-to-buy.md)。</span><span class="sxs-lookup"><span data-stu-id="34c55-125">For more information, see [What do I need to buy to use Microsoft 365 Business Voice?](what-to-buy.md).</span></span>
* <span data-ttu-id="34c55-126">**請確定您的網際網路連接可以支援 Business Voice**。</span><span class="sxs-lookup"><span data-stu-id="34c55-126">**Make sure your Internet connection can support Business Voice**.</span></span> <span data-ttu-id="34c55-127">詳細資訊，請參閱 [檢查商務用語音的網際網路連接](get-ready-internet.md)。</span><span class="sxs-lookup"><span data-stu-id="34c55-127">For more information, see [Check your Internet connection for Business Voice](get-ready-internet.md).</span></span>
* <span data-ttu-id="34c55-128">**在Teams** 裝置上設定語音信箱、設定語音信箱問候語，以及協助使用者瞭解Teams。</span><span class="sxs-lookup"><span data-stu-id="34c55-128">**Set up Teams on your users' devices**, set up voicemail greetings, and help your users learn about Teams.</span></span> <span data-ttu-id="34c55-129">如要取得詳細資訊，請參閱[如何讓我的使用者準備好Microsoft 365 商務語音？](prepare-users.md)。</span><span class="sxs-lookup"><span data-stu-id="34c55-129">For more information, see [How do I get my users ready for Microsoft 365 Business Voice?](prepare-users.md).</span></span>

<span data-ttu-id="34c55-130">準備好組織商務語音之後，請選取下一個步驟 **：開始設定商務語音**。</span><span class="sxs-lookup"><span data-stu-id="34c55-130">After you've prepare your organization for Business Voice, select **Next step: Start setting up Business Voice**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="34c55-131">下一個步驟：開始設定商務語音</span><span class="sxs-lookup"><span data-stu-id="34c55-131">Next step: Start setting up Business Voice</span></span>](set-up-emergency-locations.md)
