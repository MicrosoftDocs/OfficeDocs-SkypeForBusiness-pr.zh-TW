---
title: 設定Microsoft 365 商務語音位置
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
description: 瞭解如何設定緊急位置Microsoft 365 商務語音。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9fab5fead952837e2fb272819a600381252bcbf8
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282530"
---
# <a name="step-1-set-up-a-business-voice-emergency-location"></a><span data-ttu-id="b7858-103">步驟 1：設定商務語音緊急位置</span><span class="sxs-lookup"><span data-stu-id="b7858-103">Step 1: Set up a Business Voice emergency location</span></span>

<span data-ttu-id="b7858-104">當貴組織中有人撥打緊急服務電話時，例如火警、警車或急救車時，會使用緊急位置。</span><span class="sxs-lookup"><span data-stu-id="b7858-104">An emergency location is used when someone in your organization calls emergency services such as fire, police, or ambulance.</span></span> <span data-ttu-id="b7858-105">當人員撥打緊急服務時，已配置為貴組織的緊急位址的位址會送到服務。</span><span class="sxs-lookup"><span data-stu-id="b7858-105">When a person calls an emergency service, the address that's configured as your organization's emergency address is sent to the service.</span></span> <span data-ttu-id="b7858-106">此步驟會設定貴組織的主要緊急位置。</span><span class="sxs-lookup"><span data-stu-id="b7858-106">This step sets up the primary emergency location for your organization.</span></span> <span data-ttu-id="b7858-107">此位置將在稍後的步驟中與公司的主要電話號碼相關聯。</span><span class="sxs-lookup"><span data-stu-id="b7858-107">This location will be associated with your company's main phone number in a later step.</span></span>

<span data-ttu-id="b7858-108">如果您有多個位置的使用者，例如家用辦公室或其他城市的辦公室，您可以設定其他緊急位置。</span><span class="sxs-lookup"><span data-stu-id="b7858-108">If you have users in multiple locations, such as home offices or offices in other cities, you can configure additional emergency locations.</span></span> <span data-ttu-id="b7858-109">您甚至可以在位置中設定特定位置。</span><span class="sxs-lookup"><span data-stu-id="b7858-109">You can even configure specific places within a location.</span></span> <span data-ttu-id="b7858-110">位置可以是不同的建築物、樓層、辦公室，或是使用者可能位於位置的其他位置。</span><span class="sxs-lookup"><span data-stu-id="b7858-110">Places can be different buildings, floors, offices, or other places where users may be at a location.</span></span> <span data-ttu-id="b7858-111">完成商務語音的初始設定後，可以新增其他位置和位置。</span><span class="sxs-lookup"><span data-stu-id="b7858-111">Additional locations and places can be added after you complete your initial setup of Business Voice.</span></span>

## <a name="add-an-emergency-location"></a><span data-ttu-id="b7858-112">新增緊急位置</span><span class="sxs-lookup"><span data-stu-id="b7858-112">Add an emergency location</span></span>

1. <span data-ttu-id="b7858-113">開啟 Microsoft Teams系統管理中心，然後使用全域系統管理員使用者登入 (這通常是您用來註冊帳戶Microsoft 365) 。</span><span class="sxs-lookup"><span data-stu-id="b7858-113">Open the Microsoft Teams admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
1. <span data-ttu-id="b7858-114">在左側流覽窗格中，前往 <a href="https://admin.teams.microsoft.com/locations" target="_blank">**位置緊急**  >  **位址**</a>。</span><span class="sxs-lookup"><span data-stu-id="b7858-114">In the left navigation pane, go to <a href="https://admin.teams.microsoft.com/locations" target="_blank">**Locations** > **Emergency addresses**</a>.</span></span>
1. <span data-ttu-id="b7858-115">按一下 [新增 **]**。</span><span class="sxs-lookup"><span data-stu-id="b7858-115">Click **Add**.</span></span>
1. <span data-ttu-id="b7858-116">輸入位置的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="b7858-116">Enter a name and description for the location.</span></span>
1. <span data-ttu-id="b7858-117">選取國家/地區，然後輸入位址。</span><span class="sxs-lookup"><span data-stu-id="b7858-117">Select the country or region, and then enter the address.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b7858-118">在比利時、法國、德國、愛爾蘭、荷蘭和西班牙，必須瞭解，若要在 Microsoft 365 或 Office 365 中成功啟用電話號碼，緊急位置中用來取得號碼的位址必須與電話號碼的區碼相符。</span><span class="sxs-lookup"><span data-stu-id="b7858-118">In Belgium, France, Germany, Ireland, Netherlands, and Spain, it's important to understand that to successfully activate a phone number in Microsoft 365 or Office 365, the address set up in the emergency location, which is used to acquire the number, must match the phone number's area code.</span></span>

1. <span data-ttu-id="b7858-119">如果找不到位址，而您想要手動編輯位址，請開啟手動 **編輯位址**。</span><span class="sxs-lookup"><span data-stu-id="b7858-119">If the address isn't found and you want to manually edit the address, turn on **Edit the address manually**.</span></span>
1. <span data-ttu-id="b7858-120">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="b7858-120">Click **Save**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="b7858-121">下一個步驟：設定電話號碼</span><span class="sxs-lookup"><span data-stu-id="b7858-121">Next step: Set up phone numbers</span></span>](set-up-phone-numbers.md)
