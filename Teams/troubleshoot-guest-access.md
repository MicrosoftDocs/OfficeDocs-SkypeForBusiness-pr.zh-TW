---
title: 針對 Microsoft 團隊中的來賓存取問題進行疑難排解
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: corbinm
search.appverid: MET150
description: 在 Microsoft 團隊中取得來賓存取的疑難排解及修正問題。
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: eefaece55876bc66905716526884fd21303c630e
ms.sourcegitcommit: 09e719ead5c02b3cfa96828841c4905748d192a3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/28/2019
ms.locfileid: "37754359"
---
<a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a><span data-ttu-id="84f3c-103">針對 Microsoft 團隊中的來賓存取問題進行疑難排解</span><span class="sxs-lookup"><span data-stu-id="84f3c-103">Troubleshoot problems with guest access in Microsoft Teams</span></span>
======================================================

> [!IMPORTANT]
> <span data-ttu-id="84f3c-104">您可能需要等候長達24小時，變更才會生效。</span><span class="sxs-lookup"><span data-stu-id="84f3c-104">You may have to wait for up to 24 hours for your changes to take effect.</span></span> 


- <span data-ttu-id="84f3c-105">若要在小組中查看來賓存取的目前支援問題，請移至[團隊疑難排解](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)。</span><span class="sxs-lookup"><span data-stu-id="84f3c-105">To check for current support issues with guest access in Teams, go to [Teams Troubleshooting](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).</span></span>
- <span data-ttu-id="84f3c-106">若要查看我們是否知道您的問題，請查看[Microsoft 團隊的已知問題](Known-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="84f3c-106">To see whether we know about your problem, check out [Known issues for Microsoft Teams](Known-issues.md).</span></span>
- <span data-ttu-id="84f3c-107">來賓是您組織外部的使用者。</span><span class="sxs-lookup"><span data-stu-id="84f3c-107">Guests are users outside your organization.</span></span> <span data-ttu-id="84f3c-108">如果有人在您的組織內（包括您的員工、現場承包商或現場代理商），就不能將他們新增為來賓。</span><span class="sxs-lookup"><span data-stu-id="84f3c-108">If someone is inside your organization (including your employees, onsite contractors, or onsite agents), they can't be added as guests.</span></span> <span data-ttu-id="84f3c-109">同樣適用于您的公司。</span><span class="sxs-lookup"><span data-stu-id="84f3c-109">The same applies to your affiliates.</span></span>
- <span data-ttu-id="84f3c-110">在[團隊藍圖](https://aka.ms/teamsroadmap)中瞭解近期新增或更新的來賓存取功能。</span><span class="sxs-lookup"><span data-stu-id="84f3c-110">Find out about upcoming new or updated guest access features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="84f3c-111">在[團隊 UserVoice](https://aka.ms/TeamsUserVoice)中告訴我們您想要的專案。</span><span class="sxs-lookup"><span data-stu-id="84f3c-111">Tell us what you want in [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="84f3c-112">如果您的客人看到授權錯誤</span><span class="sxs-lookup"><span data-stu-id="84f3c-112">If your guests are seeing license errors</span></span>

<span data-ttu-id="84f3c-113">團隊中的來賓存取使用 Azure Active Directory （Azure AD）商務用企業（B2B）和授權模型。</span><span class="sxs-lookup"><span data-stu-id="84f3c-113">Guest access in Teams uses Azure Active Directory (Azure AD) Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="84f3c-114">來賓存取權包含在所有 Office 365 商務版 Premium、Office 365 企業版和 Office 365 教育版訂閱中。</span><span class="sxs-lookup"><span data-stu-id="84f3c-114">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="84f3c-115">不需要額外的 Office 365 授權。</span><span class="sxs-lookup"><span data-stu-id="84f3c-115">No additional Office 365 license is necessary.</span></span>

<span data-ttu-id="84f3c-116">如果您看到授權錯誤，請務必閱讀[Azure Active DIRECTORY B2B 授權指南](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)，以判斷授權需求，以符合您組織中的來賓存取需求。</span><span class="sxs-lookup"><span data-stu-id="84f3c-116">If you’re seeing licensing errors, make sure to read the [Azure Active Directory B2B licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) to determine licensing requirements to meet your needs for guest access in your organization.</span></span>


- <span data-ttu-id="84f3c-117">來賓授權會根據邀請的組織數來計算。</span><span class="sxs-lookup"><span data-stu-id="84f3c-117">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="84f3c-118">當您計算所需的授權數量時，請考慮這麼做。</span><span class="sxs-lookup"><span data-stu-id="84f3c-118">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="84f3c-119">無論受邀者是來自另一個 Office 365 租使用者，還是正在使用其個人電子郵件地址，都會針對您的組織計算授權。</span><span class="sxs-lookup"><span data-stu-id="84f3c-119">Licenses are counted against your organization whether the invited guests come from another Office 365 tenant or are using their personal email addresses.</span></span>

## <a name="related-topics"></a><span data-ttu-id="84f3c-120">相關主題</span><span class="sxs-lookup"><span data-stu-id="84f3c-120">Related topics</span></span>

[<span data-ttu-id="84f3c-121">團隊中的來賓存取權</span><span class="sxs-lookup"><span data-stu-id="84f3c-121">Guest access in Teams</span></span>](guest-access.md)


