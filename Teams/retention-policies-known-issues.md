---
title: Microsoft 團隊中的保留原則已知問題
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: reference
ms.service: msteams
ms.reviewer: anach
description: Microsoft 團隊保留原則目前已知問題清單。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 38fd76bff3309655cb7d2fa1f0acf18559f15220
ms.sourcegitcommit: b92b673e718e34b6ebda6de57ad69eb6651faa98
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/24/2019
ms.locfileid: "36183669"
---
# <a name="known-issues-for-retention-policies-in-microsoft-teams"></a><span data-ttu-id="dea9b-103">Microsoft 團隊中的保留原則已知問題</span><span class="sxs-lookup"><span data-stu-id="dea9b-103">Known issues for retention policies in Microsoft Teams</span></span>

<span data-ttu-id="dea9b-104">下列是追蹤及調查之小組中保留原則的已知問題。</span><span class="sxs-lookup"><span data-stu-id="dea9b-104">The following are known issues for retention policies in Teams that are being tracked and investigated.</span></span>

- <span data-ttu-id="dea9b-105">在 [小組頻道訊息位置] 列中的 [選擇團隊] 底下, 您可能會看到不是 [小組] 的 Office 365 群組。</span><span class="sxs-lookup"><span data-stu-id="dea9b-105">Under Choose Teams in the Teams Channel messages location row, you may see Office 365 Groups that are not also Teams.</span></span> <span data-ttu-id="dea9b-106">未來將會解決這個問題。</span><span class="sxs-lookup"><span data-stu-id="dea9b-106">This will be addressed in the future.</span></span>

- <span data-ttu-id="dea9b-107">在 [在團隊聊天位置] 列中選擇 [使用者] 底下, 您可能會看到 [來賓] 和 [非信箱] 使用者。</span><span class="sxs-lookup"><span data-stu-id="dea9b-107">Under Choose Users in the Teams Chat location row, you may see guests and non-mailbox users.</span></span> <span data-ttu-id="dea9b-108">保留原則並非要針對來賓進行設定, 我們正在努力從清單中移除這些原則。</span><span class="sxs-lookup"><span data-stu-id="dea9b-108">Retention policies are not meant to be set for guests, and we are working to remove these from the list.</span></span>

- <span data-ttu-id="dea9b-109">Exchange 生命週期助理 (ELC) 每天都會執行一次, 但其 SLA 是7天。</span><span class="sxs-lookup"><span data-stu-id="dea9b-109">Exchange Life Cycle assistant (ELC) runs daily, but it has an SLA of 7 days.</span></span> <span data-ttu-id="dea9b-110">因此, 如果您有小組保留原則刪除超過60天的專案, 這些專案可能會持續到67天。</span><span class="sxs-lookup"><span data-stu-id="dea9b-110">As a result, it's possible that, if you have a Teams retention policy to delete items older than 60 days, these items could persist for up to 67 days.</span></span> <span data-ttu-id="dea9b-111">這不是一種新的情況-它是在 Exchange 模型之後。</span><span class="sxs-lookup"><span data-stu-id="dea9b-111">This isn't a new situation - it follows the Exchange model.</span></span> <span data-ttu-id="dea9b-112">當然, 在大多數情況下沒有延遲。</span><span class="sxs-lookup"><span data-stu-id="dea9b-112">Of course, in most cases, there is no delay.</span></span>


| | | |
|---------|---------|---------|
|![代表決策點的圖示](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |<span data-ttu-id="dea9b-114">決策點</span><span class="sxs-lookup"><span data-stu-id="dea9b-114">Decision point</span></span>         |<span data-ttu-id="dea9b-115">貴組織需要哪些安全性與合規性功能？</span><span class="sxs-lookup"><span data-stu-id="dea9b-115">What security and compliance features does your organization require?</span></span> <span data-ttu-id="dea9b-116">貴組織是否有符合安全性與合規性商業需求的必要授權？</span><span class="sxs-lookup"><span data-stu-id="dea9b-116">Does your organization have the required licenses to meet Security and Compliance business requirements?</span></span>         |
|![代表後續步驟的圖示](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |<span data-ttu-id="dea9b-118">後續步驟</span><span class="sxs-lookup"><span data-stu-id="dea9b-118">Next steps</span></span>         |<span data-ttu-id="dea9b-119">記錄您所需的安全性與合規性功能。</span><span class="sxs-lookup"><span data-stu-id="dea9b-119">Document your required security and compliance features.</span></span>         |
