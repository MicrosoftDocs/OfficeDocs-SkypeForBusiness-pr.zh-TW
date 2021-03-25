---
title: 基本升級 PowerShell|Microsoft Teams|授予升級交互操作策略
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 瞭解當系統管理中心尚未在租使用者中亮起時，升級至 Microsoft Teams 的停止區。
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
ms.openlocfilehash: ef164ee5d93cb5491923ef3b319ae51134924cc2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120536"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a><span data-ttu-id="f9be6-103">將使用者從商務用 Skype Online 升級至 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f9be6-103">Upgrading your users from Skype for Business Online to Microsoft Teams</span></span>

> [!Note]
> <span data-ttu-id="f9be6-104">本文所述的命令是設計用來做為升級基本檢查清單 [的一](./upgrade-start-here.md) 部分。</span><span class="sxs-lookup"><span data-stu-id="f9be6-104">The commands described in this article are designed to be used as part of the [Upgrade Basic](./upgrade-start-here.md) checklist.</span></span>

<span data-ttu-id="f9be6-105">升級的技術移移層面需要通知您的使用者商務用 Skype 將會升級至 Teams，然後將他們移至 **Teams 模式** 。</span><span class="sxs-lookup"><span data-stu-id="f9be6-105">The technical migration aspects of your upgrade entail notifying your users that Skype for Business will be upgrading to Teams and then moving them to a **Teams only** mode.</span></span> <span data-ttu-id="f9be6-106">這些步驟可以透過商務用 Skype 遠端 Windows PowerShell 會話或透過 Microsoft Teams 系統管理中心完成。</span><span class="sxs-lookup"><span data-stu-id="f9be6-106">These steps can be accomplished via a Skype for Business remote Windows PowerShell session or through the Microsoft Teams admin center.</span></span>

<span data-ttu-id="f9be6-107">我們正在 Microsoft [Teams](manage-teams-skypeforbusiness-admin-center.md)系統管理中心積極推出升級工具，而且應該很快就會在租使用者上推出。</span><span class="sxs-lookup"><span data-stu-id="f9be6-107">We're actively rolling out upgrade tooling in the [Microsoft Teams admin center](manage-teams-skypeforbusiness-admin-center.md), and it should be available soon on your tenant.</span></span> <span data-ttu-id="f9be6-108">一旦推出，您可以在設定共存和升級設定中尋找移移使用者 [的資訊](./setting-your-coexistence-and-upgrade-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="f9be6-108">As soon as it's available, you can find information about migrating your users in [Setting your coexistence and upgrade settings](./setting-your-coexistence-and-upgrade-settings.md).</span></span>

<span data-ttu-id="f9be6-109">如果您今天準備好升級，可以使用下表中列出的 [PowerShell](/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) 命令。</span><span class="sxs-lookup"><span data-stu-id="f9be6-109">If you're ready to upgrade today, you can use the [PowerShell](/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) commands listed in the following table.</span></span>

| <span data-ttu-id="f9be6-110">升級基本步驟#</span><span class="sxs-lookup"><span data-stu-id="f9be6-110">Upgrade Basic step #</span></span> | <span data-ttu-id="f9be6-111">模式</span><span class="sxs-lookup"><span data-stu-id="f9be6-111">Mode</span></span> | <span data-ttu-id="f9be6-112">PowerShell 命令</span><span class="sxs-lookup"><span data-stu-id="f9be6-112">PowerShell command</span></span> |
|---|---|---|
| [<span data-ttu-id="f9be6-113">5</span><span class="sxs-lookup"><span data-stu-id="f9be6-113">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="f9be6-114">Islands + 通知商務用 Skype 使用者</span><span class="sxs-lookup"><span data-stu-id="f9be6-114">Islands + Notify the Skype for Business User</span></span><br><span data-ttu-id="f9be6-115"> (如果使用者目前處於群島模式， (使用此命令) ) </span><span class="sxs-lookup"><span data-stu-id="f9be6-115">(Use this command if users are currently in **Islands** mode (default))</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br><span data-ttu-id="f9be6-116">*(例如，$SipAddress='TestUser@contoso.com')*</span><span class="sxs-lookup"><span data-stu-id="f9be6-116">*(for example, $SipAddress='TestUser@contoso.com')*</span></span> |
| [<span data-ttu-id="f9be6-117">5</span><span class="sxs-lookup"><span data-stu-id="f9be6-117">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="f9be6-118">僅適用于商務用 Skype + 通知商務用 Skype 使用者</span><span class="sxs-lookup"><span data-stu-id="f9be6-118">Skype for Business Only + Notify the Skype for Business User</span></span> <br><span data-ttu-id="f9be6-119"> (如果使用者目前處於商務用 **Skype** 模式，請使用此命令) </span><span class="sxs-lookup"><span data-stu-id="f9be6-119">(Use this command if users are currently in **Skype for Business only** mode)</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [<span data-ttu-id="f9be6-120">7</span><span class="sxs-lookup"><span data-stu-id="f9be6-120">7</span></span>](upgrade-basic.md#step-7) | <span data-ttu-id="f9be6-121">僅 Teams</span><span class="sxs-lookup"><span data-stu-id="f9be6-121">Teams Only</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |