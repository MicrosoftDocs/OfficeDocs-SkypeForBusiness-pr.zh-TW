---
title: 基本升級 PowerShell |Microsoft 團隊 |授與升級交互操作原則
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 如果系統管理中心未在您的租使用者中亮起，請進一步瞭解升級至 Microsoft 團隊的 stopgap。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d51ff3304aae82f49023bdf461e76e4585cda296
ms.sourcegitcommit: 6acede580649588334aeb48130ab2a5d73245723
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/03/2020
ms.locfileid: "44522476"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a><span data-ttu-id="2d073-103">將您的使用者從商務用 Skype Online 升級至 Microsoft 團隊</span><span class="sxs-lookup"><span data-stu-id="2d073-103">Upgrading your users from Skype for Business Online to Microsoft Teams</span></span>

> [!Note]
> <span data-ttu-id="2d073-104">本文所述的命令是專門用來做為[升級基本](https://aka.ms/UpgradeBasic)檢查清單的一部分。</span><span class="sxs-lookup"><span data-stu-id="2d073-104">The commands described in this article are designed to be used as part of the [Upgrade Basic](https://aka.ms/UpgradeBasic) checklist.</span></span>

<span data-ttu-id="2d073-105">您升級的技術遷移層面會通知您的使用者商務用 Skype 將升級至小組，然後將他們移至 [**僅限團隊**] 模式。</span><span class="sxs-lookup"><span data-stu-id="2d073-105">The technical migration aspects of your upgrade entail notifying your users that Skype for Business will be upgrading to Teams and then moving them to a **Teams only** mode.</span></span> <span data-ttu-id="2d073-106">您可以透過商務用 Skype 遠端 Windows PowerShell 會話或透過 Microsoft 團隊系統管理中心來完成這些步驟。</span><span class="sxs-lookup"><span data-stu-id="2d073-106">These steps can be accomplished via a Skype for Business remote Windows PowerShell session or through the Microsoft Teams admin center.</span></span>

<span data-ttu-id="2d073-107">我們正積極推出[Microsoft 團隊系統管理中心](manage-teams-skypeforbusiness-admin-center.md)的升級工具，而且您的租使用者應該會在您的租使用者提供此功能。</span><span class="sxs-lookup"><span data-stu-id="2d073-107">We're actively rolling out upgrade tooling in the [Microsoft Teams admin center](manage-teams-skypeforbusiness-admin-center.md), and it should be available soon on your tenant.</span></span> <span data-ttu-id="2d073-108">只要提供，您就可以在[設定您的共存和升級設定](https://aka.ms/SkypeToTeams-SetCoexistence)中找到遷移使用者的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="2d073-108">As soon as it's available, you can find information about migrating your users in [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence).</span></span>

<span data-ttu-id="2d073-109">如果您已準備好要立即升級，您可以使用下表所列的[PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)命令。</span><span class="sxs-lookup"><span data-stu-id="2d073-109">If you're ready to upgrade today, you can use the [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) commands listed in the following table.</span></span>

| <span data-ttu-id="2d073-110">升級基本步驟#</span><span class="sxs-lookup"><span data-stu-id="2d073-110">Upgrade Basic step #</span></span> | <span data-ttu-id="2d073-111">下</span><span class="sxs-lookup"><span data-stu-id="2d073-111">Mode</span></span> | <span data-ttu-id="2d073-112">PowerShell 命令</span><span class="sxs-lookup"><span data-stu-id="2d073-112">PowerShell command</span></span> |
|---|---|---|
| [<span data-ttu-id="2d073-113">500</span><span class="sxs-lookup"><span data-stu-id="2d073-113">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="2d073-114">Islands + 通知商務用 Skype 使用者</span><span class="sxs-lookup"><span data-stu-id="2d073-114">Islands + Notify the Skype for Business User</span></span><br><span data-ttu-id="2d073-115">（如果使用者目前處於 [**孤島**] 模式（預設）），請使用此命令。</span><span class="sxs-lookup"><span data-stu-id="2d073-115">(Use this command if users are currently in **Islands** mode (default))</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br><span data-ttu-id="2d073-116">*（例如，$SipAddress = ' TestUser@contoso.com」）*</span><span class="sxs-lookup"><span data-stu-id="2d073-116">*(for example, $SipAddress='TestUser@contoso.com')*</span></span> |
| [<span data-ttu-id="2d073-117">500</span><span class="sxs-lookup"><span data-stu-id="2d073-117">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="2d073-118">僅限商務用 skype + 通知商務用 Skype 使用者</span><span class="sxs-lookup"><span data-stu-id="2d073-118">Skype for Business Only + Notify the Skype for Business User</span></span> <br><span data-ttu-id="2d073-119">（如果使用者目前在**商務用 Skype**模式中，請使用此命令）</span><span class="sxs-lookup"><span data-stu-id="2d073-119">(Use this command if users are currently in **Skype for Business only** mode)</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [<span data-ttu-id="2d073-120">utf-7</span><span class="sxs-lookup"><span data-stu-id="2d073-120">7</span></span>](upgrade-basic.md#step-7) | <span data-ttu-id="2d073-121">僅限團隊</span><span class="sxs-lookup"><span data-stu-id="2d073-121">Teams Only</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |
