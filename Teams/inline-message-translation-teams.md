---
title: 開啟內聯郵件翻譯
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
description: 瞭解如何使用 Microsoft 團隊系統管理中心或 PowerShell 開啟 Microsoft 團隊中的內嵌翻譯。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0fabdbde6f8307694457d4861d67c6ed2eb22ac1
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905805"
---
<a name="turn-on-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="c7a62-103">開啟 Microsoft 團隊中的內嵌郵件翻譯</span><span class="sxs-lookup"><span data-stu-id="c7a62-103">Turn on inline message translation in Microsoft Teams</span></span> 
=================================================

<span data-ttu-id="c7a62-104">內嵌郵件翻譯是一種新的 Microsoft 團隊功能，可讓使用者將小組訊息轉換成由 Office 365 的個人語言設定所指定的[語言](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194)。</span><span class="sxs-lookup"><span data-stu-id="c7a62-104">Inline message translation is a new Microsoft Teams feature that lets users translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings for Office 365.</span></span>

<span data-ttu-id="c7a62-105">預設會針對您的組織推出內嵌郵件翻譯。</span><span class="sxs-lookup"><span data-stu-id="c7a62-105">Inline message translation is being rolled out by default for your organization.</span></span> <span data-ttu-id="c7a62-106">如果您想要允許使用者在團隊用戶端中使用這項功能，您必須開啟此設定。</span><span class="sxs-lookup"><span data-stu-id="c7a62-106">If you want to allow users to use this feature within the Teams client, you must turn this setting on.</span></span>

> [!NOTE]
><span data-ttu-id="c7a62-107">此推出已從 office 365 政府社區版雲端和 Office 365 德國環境中的 Office 365 訂閱中排除。</span><span class="sxs-lookup"><span data-stu-id="c7a62-107">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span>

## <a name="use-powershell-to-turn-on-inline-message-translation"></a><span data-ttu-id="c7a62-108">使用 PowerShell 開啟內聯郵件轉換</span><span class="sxs-lookup"><span data-stu-id="c7a62-108">Use PowerShell to turn on inline message translation</span></span>

<span data-ttu-id="c7a62-109">您可以使用訊息策略來開啟內嵌郵件翻譯。</span><span class="sxs-lookup"><span data-stu-id="c7a62-109">You can use the messaging policy to turn on the inline message translation.</span></span>

<span data-ttu-id="c7a62-110">使用[CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) Cmdlet 開啟原則。</span><span class="sxs-lookup"><span data-stu-id="c7a62-110">Turn on the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="c7a62-111">原則需要幾分鐘的時間才能套用。</span><span class="sxs-lookup"><span data-stu-id="c7a62-111">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="c7a62-112">使用者可能需要登出並重新登入小組。</span><span class="sxs-lookup"><span data-stu-id="c7a62-112">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="use-the-microsoft-teams-admin-center-to-turn-on-inline-message-translation"></a><span data-ttu-id="c7a62-113">使用 Microsoft 團隊系統管理中心來開啟內嵌郵件翻譯</span><span class="sxs-lookup"><span data-stu-id="c7a62-113">Use the Microsoft Teams admin center to turn on inline message translation</span></span>

<span data-ttu-id="c7a62-114">在**Microsoft 團隊系統管理中心**中，從左側導覽中選取 [**訊息原則**]，然後建立新的原則或編輯現有的原則，然後將 [**允許使用者將郵件翻譯**成] 選項設定為 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="c7a62-114">In the **Microsoft Teams admin center**, select **Messaging Policies** from the left navigation, then either create a new policy or edit an existing policy, and set the **Allow users to translate messages** option to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="c7a62-115">此服務會進行翻譯並將它傳送給用戶端，而不會影響在合規性記錄中捕獲的內容。</span><span class="sxs-lookup"><span data-stu-id="c7a62-115">The service does the translation and delivers it to the client with no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="c7a62-116">若要深入瞭解翻譯，請參閱[什麼是 Microsoft Translator？](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)。</span><span class="sxs-lookup"><span data-stu-id="c7a62-116">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span></span>