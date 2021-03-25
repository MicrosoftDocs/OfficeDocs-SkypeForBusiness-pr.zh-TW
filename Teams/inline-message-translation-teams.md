---
title: 開啟內嵌郵件翻譯
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 06/21/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: salilda
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何使用 Microsoft Teams 系統管理中心或 PowerShell 在 Microsoft Teams 中開啟內嵌翻譯。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5c9e34c5e539d32b25259098973e9bfe6795ad7c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120624"
---
<a name="turn-off-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="7667a-103">在 Microsoft Teams 中關閉內嵌郵件翻譯</span><span class="sxs-lookup"><span data-stu-id="7667a-103">Turn off inline message translation in Microsoft Teams</span></span>
=================================================

<span data-ttu-id="7667a-104">內嵌郵件翻譯是 Microsoft Teams 功能，可讓使用者將 Teams[](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194)郵件翻譯成其個人語言設定所指定的語言。</span><span class="sxs-lookup"><span data-stu-id="7667a-104">Inline message translation is a Microsoft Teams feature that lets users translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings.</span></span>

<span data-ttu-id="7667a-105">內嵌郵件翻譯預設適用于貴組織。</span><span class="sxs-lookup"><span data-stu-id="7667a-105">Inline message translation is rolled out by default for your organization.</span></span> <span data-ttu-id="7667a-106">如果您想要允許使用者在 Teams 用戶端內使用此功能，就不需要進行變更。</span><span class="sxs-lookup"><span data-stu-id="7667a-106">You don't need to make changes if you want to allow users to use this feature within the Teams client.</span></span>

> [!NOTE]
><span data-ttu-id="7667a-107">在我們的 Office 365 政府社群雲端和 Office 365 Germany 環境中，這項推出方案不包含 Office 365 訂閱。</span><span class="sxs-lookup"><span data-stu-id="7667a-107">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span>

## <a name="use-powershell-to-turn-off-inline-message-translation"></a><span data-ttu-id="7667a-108">使用 PowerShell 關閉內嵌郵件翻譯</span><span class="sxs-lookup"><span data-stu-id="7667a-108">Use PowerShell to turn off inline message translation</span></span>

<span data-ttu-id="7667a-109">您可以使用訊息策略關閉內嵌郵件翻譯。</span><span class="sxs-lookup"><span data-stu-id="7667a-109">You can use the messaging policy to turn off the inline message translation.</span></span>

<span data-ttu-id="7667a-110">使用 [Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) Cmdlet 關閉該策略。</span><span class="sxs-lookup"><span data-stu-id="7667a-110">Turn off the policy by using the [Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="7667a-111">原則需要幾分鐘的時間才能適用。</span><span class="sxs-lookup"><span data-stu-id="7667a-111">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="7667a-112">使用者可能需要登出並重新登錄 Teams。</span><span class="sxs-lookup"><span data-stu-id="7667a-112">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="use-the-microsoft-teams-admin-center-to-turn-off-inline-message-translation"></a><span data-ttu-id="7667a-113">使用 Microsoft Teams 系統管理中心關閉內嵌郵件翻譯</span><span class="sxs-lookup"><span data-stu-id="7667a-113">Use the Microsoft Teams admin center to turn off inline message translation</span></span>

<span data-ttu-id="7667a-114">在 **Microsoft Teams 系統** 管理中心，從左側流覽選取訊息策略，然後建立新策略或編輯現有的策略，然後將郵件翻譯選項設為 **關閉**。</span><span class="sxs-lookup"><span data-stu-id="7667a-114">In the **Microsoft Teams admin center**, select **Messaging Policies** from the left navigation, then either create a new policy or edit an existing policy, and set the **Translate messages** option to **Off**.</span></span>

> [!NOTE]
> <span data-ttu-id="7667a-115">服務會進行翻譯，並傳送給用戶端，且對合規性記錄中捕獲的內容沒有影響。</span><span class="sxs-lookup"><span data-stu-id="7667a-115">The service does the translation and delivers it to the client with no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="7667a-116">若要深入瞭解翻譯，請參閱什麼是 [Microsoft Translator？](/azure/cognitive-services/translator/translator-info-overview)</span><span class="sxs-lookup"><span data-stu-id="7667a-116">To learn more about translation, see [What is Microsoft Translator?](/azure/cognitive-services/translator/translator-info-overview)</span></span>