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
ms.openlocfilehash: 72c6db7bdc6ff8b765afdf38bfe910552b45cbf2
ms.sourcegitcommit: 3325fd9de57367e9dd60685d1fef096921441a76
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/01/2020
ms.locfileid: "43997254"
---
<a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a><span data-ttu-id="403b2-103">針對 Microsoft Teams 中的來賓存取問題進行疑難排解</span><span class="sxs-lookup"><span data-stu-id="403b2-103">Troubleshoot problems with guest access in Microsoft Teams</span></span>
======================================================

> [!IMPORTANT]
> <span data-ttu-id="403b2-104">您可能需要等候 24 小時，變更才會生效。</span><span class="sxs-lookup"><span data-stu-id="403b2-104">You may have to wait up to 24 hours for your changes to take effect.</span></span> 


- <span data-ttu-id="403b2-105">若要查看我們是否知道您的問題，請參閱[貴組織中的支援小組](Known-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="403b2-105">To see whether we know about your problem, check out [Support Teams in your organization](Known-issues.md).</span></span>
- <span data-ttu-id="403b2-106">若要查看 Teams 中的來賓存取的最新支援問題，請移至 [Teams 疑難排解](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)。</span><span class="sxs-lookup"><span data-stu-id="403b2-106">To check for current support issues with guest access in Teams, go to [Teams Troubleshooting](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).</span></span>
- <span data-ttu-id="403b2-107">來賓是指貴組織外的使用者。</span><span class="sxs-lookup"><span data-stu-id="403b2-107">Guests are users outside your organization.</span></span> <span data-ttu-id="403b2-108">如果某人在組織內 (包括您的員工、現場承包商或現場代理商)，他們就無法新增為來賓。</span><span class="sxs-lookup"><span data-stu-id="403b2-108">If someone is inside your organization (including your employees, onsite contractors, or onsite agents), they can't be added as guests.</span></span> <span data-ttu-id="403b2-109">這同樣適用於您的子公司。</span><span class="sxs-lookup"><span data-stu-id="403b2-109">The same applies to your affiliates.</span></span>
- <span data-ttu-id="403b2-110">瞭解 [Teams 藍圖](https://aka.ms/teamsroadmap)中近期新增或更新的來賓存取功能。</span><span class="sxs-lookup"><span data-stu-id="403b2-110">Find out about upcoming new or updated guest access features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="403b2-111">在 [Teams UserVoice](https://aka.ms/TeamsUserVoice)中告訴我們您想要的內容。</span><span class="sxs-lookup"><span data-stu-id="403b2-111">Tell us what you want in [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="403b2-112">如果您的來賓看到授權錯誤</span><span class="sxs-lookup"><span data-stu-id="403b2-112">If your guests are seeing license errors</span></span>

<span data-ttu-id="403b2-113">Teams 中的來賓存取使用 Azure Active Directory (Azure AD) 企業對企業 (B2B) 及其授權模型。</span><span class="sxs-lookup"><span data-stu-id="403b2-113">Guest access in Teams uses Azure Active Directory (Azure AD) Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="403b2-114">來賓存取隨附於所有 Microsoft 365 商務標準版、Office 365 企業版和 Office 365 教育版訂閱。</span><span class="sxs-lookup"><span data-stu-id="403b2-114">Guest access is included with all Microsoft 365 Business Standard, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="403b2-115">您不需要額外的 Office 365 授權。</span><span class="sxs-lookup"><span data-stu-id="403b2-115">No additional Office 365 license is necessary.</span></span>

> [!NOTE]
> <span data-ttu-id="403b2-116">您必須在來賓的家用租使用者上啟用團隊，才能在另一個（資源）租使用者上以來賓身分登入和使用團隊。</span><span class="sxs-lookup"><span data-stu-id="403b2-116">Teams must be enabled on a guest's home tenant for guests to be able to sign in and use Teams as a guest on another (resource) tenant.</span></span>

<span data-ttu-id="403b2-117">如果您看到授權錯誤，請務必閱讀[Azure Active DIRECTORY B2B 授權指南](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)，以判斷授權需求，以符合您組織中的來賓存取需求。</span><span class="sxs-lookup"><span data-stu-id="403b2-117">If you're seeing licensing errors, make sure to read the [Azure Active Directory B2B licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) to determine licensing requirements to meet your needs for guest access in your organization.</span></span>


- <span data-ttu-id="403b2-118">系統會針對邀請的組織計算來賓授權。</span><span class="sxs-lookup"><span data-stu-id="403b2-118">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="403b2-119">當您計算所需的授權數量時，請考慮這一點。</span><span class="sxs-lookup"><span data-stu-id="403b2-119">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="403b2-120">無論受邀的來賓是來自另一個 Office 365 組織，還是正在使用其個人電子郵件地址，都會針對您的組織計算授權。</span><span class="sxs-lookup"><span data-stu-id="403b2-120">Licenses are counted against your organization whether the invited guests come from another Office 365 organization or are using their personal email addresses.</span></span>

## <a name="support-for-b2b-user-types"></a><span data-ttu-id="403b2-121">B2B 使用者類型的支援</span><span class="sxs-lookup"><span data-stu-id="403b2-121">Support for B2B User types</span></span>
<span data-ttu-id="403b2-122">目前，Teams 就如同 [Azure B2B 所定義](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)，只支援狀態 1 和狀態 2 類型的來賓使用者。</span><span class="sxs-lookup"><span data-stu-id="403b2-122">Currently Teams only has support for State 1 and State 2 types of Guest users [as defined by Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).</span></span>

## <a name="related-topics"></a><span data-ttu-id="403b2-123">相關主題</span><span class="sxs-lookup"><span data-stu-id="403b2-123">Related topics</span></span>

[<span data-ttu-id="403b2-124">Teams 中的來賓存取</span><span class="sxs-lookup"><span data-stu-id="403b2-124">Guest access in Teams</span></span>](guest-access.md)


