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
ms.openlocfilehash: e0a3530b7a1f9029d9f671d0a02ef58cbb7907bf
ms.sourcegitcommit: 96d98e145ff300833d827a7d43b4e4b0331b7538
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/05/2019
ms.locfileid: "39871729"
---
<a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a><span data-ttu-id="15dcd-103">針對 Microsoft 團隊中的來賓存取問題進行疑難排解</span><span class="sxs-lookup"><span data-stu-id="15dcd-103">Troubleshoot problems with guest access in Microsoft Teams</span></span>
======================================================

> [!IMPORTANT]
> <span data-ttu-id="15dcd-104">您可能必須等候長達24小時，變更才會生效。</span><span class="sxs-lookup"><span data-stu-id="15dcd-104">You may have to wait up to 24 hours for your changes to take effect.</span></span> 


- <span data-ttu-id="15dcd-105">若要在小組中查看來賓存取的目前支援問題，請移至[團隊疑難排解](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)。</span><span class="sxs-lookup"><span data-stu-id="15dcd-105">To check for current support issues with guest access in Teams, go to [Teams Troubleshooting](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).</span></span>
- <span data-ttu-id="15dcd-106">若要查看我們是否知道您的問題，請查看[Microsoft 團隊的已知問題](Known-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="15dcd-106">To see whether we know about your problem, check out [Known issues for Microsoft Teams](Known-issues.md).</span></span>
- <span data-ttu-id="15dcd-107">來賓是您組織外部的使用者。</span><span class="sxs-lookup"><span data-stu-id="15dcd-107">Guests are users outside your organization.</span></span> <span data-ttu-id="15dcd-108">如果有人在您的組織內（包括您的員工、現場承包商或現場代理商），就不能將他們新增為來賓。</span><span class="sxs-lookup"><span data-stu-id="15dcd-108">If someone is inside your organization (including your employees, onsite contractors, or onsite agents), they can't be added as guests.</span></span> <span data-ttu-id="15dcd-109">同樣適用于您的公司。</span><span class="sxs-lookup"><span data-stu-id="15dcd-109">The same applies to your affiliates.</span></span>
- <span data-ttu-id="15dcd-110">在[團隊藍圖](https://aka.ms/teamsroadmap)中瞭解近期新增或更新的來賓存取功能。</span><span class="sxs-lookup"><span data-stu-id="15dcd-110">Find out about upcoming new or updated guest access features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="15dcd-111">在[團隊 UserVoice](https://aka.ms/TeamsUserVoice)中告訴我們您想要的專案。</span><span class="sxs-lookup"><span data-stu-id="15dcd-111">Tell us what you want in [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="15dcd-112">如果您的客人看到授權錯誤</span><span class="sxs-lookup"><span data-stu-id="15dcd-112">If your guests are seeing license errors</span></span>

<span data-ttu-id="15dcd-113">團隊中的來賓存取使用 Azure Active Directory （Azure AD）商務用企業（B2B）和授權模型。</span><span class="sxs-lookup"><span data-stu-id="15dcd-113">Guest access in Teams uses Azure Active Directory (Azure AD) Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="15dcd-114">來賓存取隨附於所有 Office 365 商務進階版、Office 365 企業版和 Office 365 教育版訂閱。</span><span class="sxs-lookup"><span data-stu-id="15dcd-114">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="15dcd-115">您不需要額外的 Office 365 授權。</span><span class="sxs-lookup"><span data-stu-id="15dcd-115">No additional Office 365 license is necessary.</span></span>

<span data-ttu-id="15dcd-116">如果您看到授權錯誤，請務必閱讀[Azure Active DIRECTORY B2B 授權指南](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)，以判斷授權需求，以符合您組織中的來賓存取需求。</span><span class="sxs-lookup"><span data-stu-id="15dcd-116">If you’re seeing licensing errors, make sure to read the [Azure Active Directory B2B licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) to determine licensing requirements to meet your needs for guest access in your organization.</span></span>


- <span data-ttu-id="15dcd-117">來賓授權會根據邀請的組織數來計算。</span><span class="sxs-lookup"><span data-stu-id="15dcd-117">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="15dcd-118">當您計算所需的授權數量時，請考慮這麼做。</span><span class="sxs-lookup"><span data-stu-id="15dcd-118">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="15dcd-119">無論受邀者是來自另一個 Office 365 租使用者，還是正在使用其個人電子郵件地址，都會針對您的組織計算授權。</span><span class="sxs-lookup"><span data-stu-id="15dcd-119">Licenses are counted against your organization whether the invited guests come from another Office 365 tenant or are using their personal email addresses.</span></span>

## <a name="support-for-b2b-user-types"></a><span data-ttu-id="15dcd-120">對 B2B 使用者類型的支援</span><span class="sxs-lookup"><span data-stu-id="15dcd-120">Support for B2B User types</span></span>
<span data-ttu-id="15dcd-121">目前的團隊只支援[由 AZURE B2B 所定義](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)的狀態1和狀態2類型的來賓使用者。</span><span class="sxs-lookup"><span data-stu-id="15dcd-121">Currently Teams only has support for State 1 and State 2 types of Guest users [as defined by Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).</span></span>

## <a name="related-topics"></a><span data-ttu-id="15dcd-122">相關主題</span><span class="sxs-lookup"><span data-stu-id="15dcd-122">Related topics</span></span>

[<span data-ttu-id="15dcd-123">Teams 中的來賓存取</span><span class="sxs-lookup"><span data-stu-id="15dcd-123">Guest access in Teams</span></span>](guest-access.md)


