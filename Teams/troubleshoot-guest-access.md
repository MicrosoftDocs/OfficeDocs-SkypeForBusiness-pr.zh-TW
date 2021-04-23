---
title: 針對 Microsoft Teams 中的來賓存取問題進行疑難排解
ms.author: mikeplum
author: MikePlumleyMSFT
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
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0468d0d3d1cc7a8d1c17699e28c1449e1f7800c8
ms.sourcegitcommit: a731226d62d8b23fe73bd7bf61654e16367fbd90
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2021
ms.locfileid: "51948679"
---
# <a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a><span data-ttu-id="fe5cc-103">針對 Microsoft Teams 中的來賓存取問題進行疑難排解</span><span class="sxs-lookup"><span data-stu-id="fe5cc-103">Troubleshoot problems with guest access in Microsoft Teams</span></span>

- <span data-ttu-id="fe5cc-104">若要瞭解我們是否知道您的問題，請參閱 [貴組織的支援小組](/MicrosoftTeams/troubleshoot/teams-welcome)。</span><span class="sxs-lookup"><span data-stu-id="fe5cc-104">To see whether we know about your problem, check out [Support Teams in your organization](/MicrosoftTeams/troubleshoot/teams-welcome).</span></span>
- <span data-ttu-id="fe5cc-105">若要查看 Teams 中的來賓存取的最新支援問題，請移至 [Teams 疑難排解](/MicrosoftTeams/troubleshoot/)。</span><span class="sxs-lookup"><span data-stu-id="fe5cc-105">To check for current support issues with guest access in Teams, go to [Teams Troubleshooting](/MicrosoftTeams/troubleshoot/).</span></span>
- <span data-ttu-id="fe5cc-106">來賓是貴組織外部人員。</span><span class="sxs-lookup"><span data-stu-id="fe5cc-106">Guests are people outside your organization.</span></span> <span data-ttu-id="fe5cc-107">如果某人在組織內 (包括您的員工、現場承包商或現場代理商)，他們就無法新增為來賓。</span><span class="sxs-lookup"><span data-stu-id="fe5cc-107">If someone is inside your organization (including your employees, onsite contractors, or onsite agents), they can't be added as guests.</span></span> <span data-ttu-id="fe5cc-108">這同樣適用於您的子公司。</span><span class="sxs-lookup"><span data-stu-id="fe5cc-108">The same applies to your affiliates.</span></span>
- <span data-ttu-id="fe5cc-109">瞭解 [Teams 藍圖](https://aka.ms/teamsroadmap)中近期新增或更新的來賓存取功能。</span><span class="sxs-lookup"><span data-stu-id="fe5cc-109">Find out about upcoming new or updated guest access features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="fe5cc-110">在 [Teams UserVoice](https://aka.ms/TeamsUserVoice)中告訴我們您想要的內容。</span><span class="sxs-lookup"><span data-stu-id="fe5cc-110">Tell us what you want in [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>

[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="fe5cc-111">如果您的來賓看到授權錯誤</span><span class="sxs-lookup"><span data-stu-id="fe5cc-111">If your guests are seeing license errors</span></span>

<span data-ttu-id="fe5cc-112">Teams 中的來賓存取使用 Azure Active Directory (Azure AD) 企業對企業 (B2B) 及其授權模型。</span><span class="sxs-lookup"><span data-stu-id="fe5cc-112">Guest access in Teams uses Azure Active Directory (Azure AD) Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="fe5cc-113">來賓存取隨附於所有 Microsoft 365 商務標準版、Office 365 企業版和 Office 365 教育版訂閱。</span><span class="sxs-lookup"><span data-stu-id="fe5cc-113">Guest access is included with all Microsoft 365 Business Standard, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="fe5cc-114">您不需要額外的 Microsoft 365 或 Office 365 授權。</span><span class="sxs-lookup"><span data-stu-id="fe5cc-114">No additional Microsoft 365 or Office 365 license is necessary.</span></span>

> [!NOTE]
> <span data-ttu-id="fe5cc-115">來賓的家用租使用者必須啟用 Teams，來賓才能在另一個資源或租使用者上以來賓 (Teams) 使用。</span><span class="sxs-lookup"><span data-stu-id="fe5cc-115">Teams must be enabled on a guest's home tenant for guests to be able to sign in and use Teams as a guest on another (resource) tenant.</span></span>

<span data-ttu-id="fe5cc-116">如果您看到授權錯誤，請務必閱讀 [Azure AD 外部](/azure/active-directory/external-identities/external-identities-pricing) 身分標識的帳單模型，以判斷授權需求，以滿足貴組織中來賓存取的需求。</span><span class="sxs-lookup"><span data-stu-id="fe5cc-116">If you're seeing licensing errors, make sure to read the [Billing model for Azure AD External Identities](/azure/active-directory/external-identities/external-identities-pricing) to determine licensing requirements to meet your needs for guest access in your organization.</span></span>

- <span data-ttu-id="fe5cc-117">系統會針對邀請的組織計算來賓授權。</span><span class="sxs-lookup"><span data-stu-id="fe5cc-117">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="fe5cc-118">當您計算所需的授權數量時，請考慮這一點。</span><span class="sxs-lookup"><span data-stu-id="fe5cc-118">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="fe5cc-119">無論受邀來賓來自另一個 Microsoft 365 組織，或正在使用其個人電子郵件地址，授權會計入貴組織。</span><span class="sxs-lookup"><span data-stu-id="fe5cc-119">Licenses are counted against your organization whether the invited guests come from another Microsoft 365 organization or are using their personal email addresses.</span></span>

## <a name="support-for-b2b-user-types"></a><span data-ttu-id="fe5cc-120">B2B 使用者類型的支援</span><span class="sxs-lookup"><span data-stu-id="fe5cc-120">Support for B2B User types</span></span>

<span data-ttu-id="fe5cc-121">目前，Teams 就如同 [Azure B2B 所定義](/azure/active-directory/b2b/user-properties)，只支援狀態 1 和狀態 2 類型的來賓使用者。</span><span class="sxs-lookup"><span data-stu-id="fe5cc-121">Currently Teams only has support for State 1 and State 2 types of Guest users [as defined by Azure B2B](/azure/active-directory/b2b/user-properties).</span></span>

## <a name="related-topics"></a><span data-ttu-id="fe5cc-122">相關主題</span><span class="sxs-lookup"><span data-stu-id="fe5cc-122">Related topics</span></span>

[<span data-ttu-id="fe5cc-123">Teams 中的來賓存取</span><span class="sxs-lookup"><span data-stu-id="fe5cc-123">Guest access in Teams</span></span>](guest-access.md)

[<span data-ttu-id="fe5cc-124">Teams 疑難排解</span><span class="sxs-lookup"><span data-stu-id="fe5cc-124">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)