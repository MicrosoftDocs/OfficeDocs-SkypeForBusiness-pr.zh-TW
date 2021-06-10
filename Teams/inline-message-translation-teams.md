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
description: 瞭解如何使用系統管理中心或 PowerShell 在 Microsoft Teams中開啟Microsoft Teams翻譯。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 78282b464dd1d9cb25c5d4d2b338c74a2c91d374
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2021
ms.locfileid: "52855922"
---
# <a name="turn-off-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="18035-103">在郵件中關閉內嵌郵件翻譯Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="18035-103">Turn off inline message translation in Microsoft Teams</span></span>

<span data-ttu-id="18035-104">內嵌郵件翻譯是一項Microsoft Teams功能，可讓使用者將Teams訊息翻譯成其個人語言設定[](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194)所指定的語言。</span><span class="sxs-lookup"><span data-stu-id="18035-104">Inline message translation is a Microsoft Teams feature that lets users translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings.</span></span>

<span data-ttu-id="18035-105">根據預設，貴組織會推出內嵌郵件翻譯。</span><span class="sxs-lookup"><span data-stu-id="18035-105">Inline message translation is rolled out by default for your organization.</span></span> <span data-ttu-id="18035-106">如果您想要允許使用者在用戶端內使用這項功能，Teams變更。</span><span class="sxs-lookup"><span data-stu-id="18035-106">You don't need to make changes if you want to allow users to use this feature within the Teams client.</span></span>

> [!NOTE]
><span data-ttu-id="18035-107">在我們的雲端和德國Office 365中，Office 365 政府版 Community方案Office 365推出。</span><span class="sxs-lookup"><span data-stu-id="18035-107">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span>

## <a name="use-powershell-to-turn-off-inline-message-translation"></a><span data-ttu-id="18035-108">使用 PowerShell 關閉內嵌郵件翻譯</span><span class="sxs-lookup"><span data-stu-id="18035-108">Use PowerShell to turn off inline message translation</span></span>

<span data-ttu-id="18035-109">您可以使用訊息策略關閉內嵌郵件翻譯。</span><span class="sxs-lookup"><span data-stu-id="18035-109">You can use the messaging policy to turn off the inline message translation.</span></span>

<span data-ttu-id="18035-110">使用 [Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) Cmdlet 關閉該策略。</span><span class="sxs-lookup"><span data-stu-id="18035-110">Turn off the policy by using the [Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="18035-111">原則需要幾分鐘的時間才能適用。</span><span class="sxs-lookup"><span data-stu-id="18035-111">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="18035-112">使用者可能需要登出並重新Teams。</span><span class="sxs-lookup"><span data-stu-id="18035-112">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="use-the-microsoft-teams-admin-center-to-turn-off-inline-message-translation"></a><span data-ttu-id="18035-113">使用 Microsoft Teams管理中心關閉內嵌郵件翻譯</span><span class="sxs-lookup"><span data-stu-id="18035-113">Use the Microsoft Teams admin center to turn off inline message translation</span></span>

<span data-ttu-id="18035-114">在 **Microsoft Teams管理** 中心中，從左側流覽選取訊息策略，然後建立新策略或編輯現有的策略，然後將郵件選項設為關閉 **。** </span><span class="sxs-lookup"><span data-stu-id="18035-114">In the **Microsoft Teams admin center**, select **Messaging Policies** from the left navigation, then either create a new policy or edit an existing policy, and set the **Translate messages** option to **Off**.</span></span>

> [!NOTE]
> <span data-ttu-id="18035-115">服務會進行翻譯，並傳送給用戶端，且對合規性記錄中捕獲的內容沒有影響。</span><span class="sxs-lookup"><span data-stu-id="18035-115">The service does the translation and delivers it to the client with no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="18035-116">若要深入瞭解翻譯，請參閱什麼是[Microsoft 翻譯工具？](/azure/cognitive-services/translator/translator-info-overview)</span><span class="sxs-lookup"><span data-stu-id="18035-116">To learn more about translation, see [What is Microsoft Translator?](/azure/cognitive-services/translator/translator-info-overview)</span></span>