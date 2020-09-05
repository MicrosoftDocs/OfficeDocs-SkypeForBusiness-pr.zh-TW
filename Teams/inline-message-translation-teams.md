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
ms.openlocfilehash: 012f2431ec7fb249a2f2e3b963c41166c4649a5c
ms.sourcegitcommit: 2e6b0930645cd97dbd597e9346a6fe1788c6facf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/04/2020
ms.locfileid: "47395382"
---
<a name="turn-off-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="a948a-103">在 Microsoft 團隊中關閉內嵌郵件翻譯</span><span class="sxs-lookup"><span data-stu-id="a948a-103">Turn off inline message translation in Microsoft Teams</span></span>
=================================================

<span data-ttu-id="a948a-104">內嵌郵件翻譯是 Microsoft 團隊的功能，可讓使用者將小組訊息轉換成其個人語言設定所指定的 [語言](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) 。</span><span class="sxs-lookup"><span data-stu-id="a948a-104">Inline message translation is a Microsoft Teams feature that lets users translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings.</span></span>

<span data-ttu-id="a948a-105">預設會針對您的組織推出內嵌郵件翻譯。</span><span class="sxs-lookup"><span data-stu-id="a948a-105">Inline message translation is rolled out by default for your organization.</span></span> <span data-ttu-id="a948a-106">如果您想要允許使用者在團隊用戶端中使用這項功能，就不需要進行變更。</span><span class="sxs-lookup"><span data-stu-id="a948a-106">You don't need to make changes if you want to allow users to use this feature within the Teams client.</span></span>

> [!NOTE]
><span data-ttu-id="a948a-107">此推出已從 office 365 政府社區版雲端和 Office 365 德國環境中的 Office 365 訂閱中排除。</span><span class="sxs-lookup"><span data-stu-id="a948a-107">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span>

## <a name="use-powershell-to-turn-off-inline-message-translation"></a><span data-ttu-id="a948a-108">使用 PowerShell 關閉內聯郵件轉換</span><span class="sxs-lookup"><span data-stu-id="a948a-108">Use PowerShell to turn off inline message translation</span></span>

<span data-ttu-id="a948a-109">您可以使用訊息策略來關閉內嵌郵件翻譯。</span><span class="sxs-lookup"><span data-stu-id="a948a-109">You can use the messaging policy to turn off the inline message translation.</span></span>

<span data-ttu-id="a948a-110">使用 [CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) Cmdlet 關閉原則。</span><span class="sxs-lookup"><span data-stu-id="a948a-110">Turn off the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="a948a-111">原則需要幾分鐘的時間才能套用。</span><span class="sxs-lookup"><span data-stu-id="a948a-111">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="a948a-112">使用者可能需要登出並重新登入小組。</span><span class="sxs-lookup"><span data-stu-id="a948a-112">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="use-the-microsoft-teams-admin-center-to-turn-off-inline-message-translation"></a><span data-ttu-id="a948a-113">使用 Microsoft 團隊系統管理中心關閉內嵌郵件翻譯</span><span class="sxs-lookup"><span data-stu-id="a948a-113">Use the Microsoft Teams admin center to turn off inline message translation</span></span>

<span data-ttu-id="a948a-114">在 **Microsoft 團隊系統管理中心**中，從左側導覽中選取 [ **訊息原則** ]，然後建立新的原則或編輯現有的原則，並將 [ **翻譯郵件** ] 選項設定為 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="a948a-114">In the **Microsoft Teams admin center**, select **Messaging Policies** from the left navigation, then either create a new policy or edit an existing policy, and set the **Translate messages** option to **Off**.</span></span>

> [!NOTE]
> <span data-ttu-id="a948a-115">此服務會進行翻譯並將它傳送給用戶端，而不會影響在合規性記錄中捕獲的內容。</span><span class="sxs-lookup"><span data-stu-id="a948a-115">The service does the translation and delivers it to the client with no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="a948a-116">若要深入瞭解翻譯，請參閱 [什麼是 Microsoft Translator？](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)</span><span class="sxs-lookup"><span data-stu-id="a948a-116">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)</span></span>
