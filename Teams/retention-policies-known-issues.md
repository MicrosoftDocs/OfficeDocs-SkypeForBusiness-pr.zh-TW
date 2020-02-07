---
title: Microsoft 團隊中的保留原則已知問題
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anach
description: Microsoft 團隊保留原則目前已知問題清單。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: d070180505081971eca6c4075bd5bc4563bcd184
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41838203"
---
# <a name="known-issues-for-retention-policies-in-microsoft-teams"></a><span data-ttu-id="83ce2-103">Microsoft 團隊中的保留原則已知問題</span><span class="sxs-lookup"><span data-stu-id="83ce2-103">Known issues for retention policies in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="83ce2-104">我們還不支援保留私人通道訊息的設定。</span><span class="sxs-lookup"><span data-stu-id="83ce2-104">We don’t yet support configuration for retention of private channel messages.</span></span> <span data-ttu-id="83ce2-105">支援在私人通道中共用的檔案保留。</span><span class="sxs-lookup"><span data-stu-id="83ce2-105">Retention of files shared in private channels is supported.</span></span>

<span data-ttu-id="83ce2-106">下列是追蹤及調查之小組中保留原則的已知問題。</span><span class="sxs-lookup"><span data-stu-id="83ce2-106">The following are known issues for retention policies in Teams that are being tracked and investigated.</span></span>

- <span data-ttu-id="83ce2-107">在 [小組頻道訊息位置] 列中的 [選擇團隊] 底下，您可能會看到不是 [小組] 的 Office 365 群組。</span><span class="sxs-lookup"><span data-stu-id="83ce2-107">Under Choose Teams in the Teams Channel messages location row, you may see Office 365 Groups that are not also Teams.</span></span> <span data-ttu-id="83ce2-108">未來將會解決這個問題。</span><span class="sxs-lookup"><span data-stu-id="83ce2-108">This will be addressed in the future.</span></span>

- <span data-ttu-id="83ce2-109">在 [在團隊聊天位置] 列中選擇 [使用者] 底下，您可能會看到 [來賓] 和 [非信箱] 使用者。</span><span class="sxs-lookup"><span data-stu-id="83ce2-109">Under Choose Users in the Teams Chat location row, you may see guests and non-mailbox users.</span></span> <span data-ttu-id="83ce2-110">保留原則並非要針對來賓進行設定，我們正在努力從清單中移除這些原則。</span><span class="sxs-lookup"><span data-stu-id="83ce2-110">Retention policies are not meant to be set for guests, and we are working to remove these from the list.</span></span>

- <span data-ttu-id="83ce2-111">Exchange 生命週期助理（ELC）每天都會執行一次，但其 SLA 是7天。</span><span class="sxs-lookup"><span data-stu-id="83ce2-111">Exchange Life Cycle assistant (ELC) runs daily, but it has an SLA of 7 days.</span></span> <span data-ttu-id="83ce2-112">因此，如果您有小組保留原則刪除超過60天的專案，這些專案可能會持續到67天。</span><span class="sxs-lookup"><span data-stu-id="83ce2-112">As a result, it's possible that, if you have a Teams retention policy to delete items older than 60 days, these items could persist for up to 67 days.</span></span> <span data-ttu-id="83ce2-113">這不是一種新的情況-它是在 Exchange 模型之後。</span><span class="sxs-lookup"><span data-stu-id="83ce2-113">This isn't a new situation - it follows the Exchange model.</span></span> <span data-ttu-id="83ce2-114">當然，在大多數情況下沒有延遲。</span><span class="sxs-lookup"><span data-stu-id="83ce2-114">Of course, in most cases, there is no delay.</span></span>


| | | |
|---------|---------|---------|
|![代表決策點的圖示](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |<span data-ttu-id="83ce2-116">決策點</span><span class="sxs-lookup"><span data-stu-id="83ce2-116">Decision point</span></span>         |<span data-ttu-id="83ce2-117">貴組織需要哪些安全性與合規性功能？</span><span class="sxs-lookup"><span data-stu-id="83ce2-117">What security and compliance features does your organization require?</span></span> <span data-ttu-id="83ce2-118">貴組織是否有符合安全性與合規性商業需求的必要授權？</span><span class="sxs-lookup"><span data-stu-id="83ce2-118">Does your organization have the required licenses to meet Security and Compliance business requirements?</span></span>         |
|![代表後續步驟的圖示](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |<span data-ttu-id="83ce2-120">後續步驟</span><span class="sxs-lookup"><span data-stu-id="83ce2-120">Next steps</span></span>         |<span data-ttu-id="83ce2-121">記錄您所需的安全性與合規性功能。</span><span class="sxs-lookup"><span data-stu-id="83ce2-121">Document your required security and compliance features.</span></span>         |
