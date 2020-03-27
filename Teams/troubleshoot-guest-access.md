---
title: 針對 Microsoft Teams 中的來賓存取問題進行疑難排解
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
description: 取得針對 Microsoft Teams 中的來賓存取問題進行疑難排解並修正問題的說明。
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 0c0f65f7026e6c083d9230551d689f0dd19d6b0d
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837633"
---
<a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a><span data-ttu-id="d298a-103">針對 Microsoft Teams 中的來賓存取問題進行疑難排解</span><span class="sxs-lookup"><span data-stu-id="d298a-103">Troubleshoot problems with guest access in Microsoft Teams</span></span>
======================================================

> [!IMPORTANT]
> <span data-ttu-id="d298a-104">您可能需要等候 24 小時，變更才會生效。</span><span class="sxs-lookup"><span data-stu-id="d298a-104">You may have to wait up to 24 hours for your changes to take effect.</span></span> 


- <span data-ttu-id="d298a-105">若要查看 Teams 中的來賓存取的最新支援問題，請移至 [Teams 疑難排解](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)。</span><span class="sxs-lookup"><span data-stu-id="d298a-105">To check for current support issues with guest access in Teams, go to [Teams Troubleshooting](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).</span></span>
- <span data-ttu-id="d298a-106">若要查看我們是否已經知道您的問題，請參閱 [Microsoft Teams 的已知問題](Known-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="d298a-106">To see whether we know about your problem, check out [Known issues for Microsoft Teams](Known-issues.md).</span></span>
- <span data-ttu-id="d298a-107">來賓是指貴組織外的使用者。</span><span class="sxs-lookup"><span data-stu-id="d298a-107">Guests are users outside your organization.</span></span> <span data-ttu-id="d298a-108">如果某人在組織內 (包括您的員工、現場承包商或現場代理商)，他們就無法新增為來賓。</span><span class="sxs-lookup"><span data-stu-id="d298a-108">If someone is inside your organization (including your employees, onsite contractors, or onsite agents), they can't be added as guests.</span></span> <span data-ttu-id="d298a-109">這同樣適用於您的子公司。</span><span class="sxs-lookup"><span data-stu-id="d298a-109">The same applies to your affiliates.</span></span>
- <span data-ttu-id="d298a-110">瞭解 [Teams 藍圖](https://aka.ms/teamsroadmap)中近期新增或更新的來賓存取功能。</span><span class="sxs-lookup"><span data-stu-id="d298a-110">Find out about upcoming new or updated guest access features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="d298a-111">在 [Teams UserVoice](https://aka.ms/TeamsUserVoice)中告訴我們您想要的內容。</span><span class="sxs-lookup"><span data-stu-id="d298a-111">Tell us what you want in [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="d298a-112">如果您的來賓看到授權錯誤</span><span class="sxs-lookup"><span data-stu-id="d298a-112">If your guests are seeing license errors</span></span>

<span data-ttu-id="d298a-113">Teams 中的來賓存取使用 Azure Active Directory (Azure AD) 企業對企業 (B2B) 及其授權模型。</span><span class="sxs-lookup"><span data-stu-id="d298a-113">Guest access in Teams uses Azure Active Directory (Azure AD) Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="d298a-114">來賓存取隨附於所有 Office 365 商務進階版、Office 365 企業版和 Office 365 教育版訂閱。</span><span class="sxs-lookup"><span data-stu-id="d298a-114">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="d298a-115">您不需要額外的 Office 365 授權。</span><span class="sxs-lookup"><span data-stu-id="d298a-115">No additional Office 365 license is necessary.</span></span>

<span data-ttu-id="d298a-116">如果您看到授權錯誤，請務必閱讀 [Azure Active Directory B2B 授權指南](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)，判斷符合您組織中來賓存取需求的授權需求。</span><span class="sxs-lookup"><span data-stu-id="d298a-116">If you’re seeing licensing errors, make sure to read the [Azure Active Directory B2B licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) to determine licensing requirements to meet your needs for guest access in your organization.</span></span>


- <span data-ttu-id="d298a-117">系統會針對邀請的組織計算來賓授權。</span><span class="sxs-lookup"><span data-stu-id="d298a-117">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="d298a-118">當您計算所需的授權數量時，請考慮這一點。</span><span class="sxs-lookup"><span data-stu-id="d298a-118">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="d298a-119">系統會針對您的組織計算授權，無論受邀的來賓是來自另一個 Office 365 租用戶，還是使用他們的個人電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="d298a-119">Licenses are counted against your organization whether the invited guests come from another Office 365 tenant or are using their personal email addresses.</span></span>

## <a name="support-for-b2b-user-types"></a><span data-ttu-id="d298a-120">B2B 使用者類型的支援</span><span class="sxs-lookup"><span data-stu-id="d298a-120">Support for B2B User types</span></span>
<span data-ttu-id="d298a-121">目前，Teams 就如同 [Azure B2B 所定義](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)，只支援狀態 1 和狀態 2 類型的來賓使用者。</span><span class="sxs-lookup"><span data-stu-id="d298a-121">Currently Teams only has support for State 1 and State 2 types of Guest users [as defined by Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).</span></span>

## <a name="related-topics"></a><span data-ttu-id="d298a-122">相關主題</span><span class="sxs-lookup"><span data-stu-id="d298a-122">Related topics</span></span>

[<span data-ttu-id="d298a-123">Teams 中的來賓存取</span><span class="sxs-lookup"><span data-stu-id="d298a-123">Guest access in Teams</span></span>](guest-access.md)


