---
title: 開啟 Microsoft 團隊中的內嵌郵件翻譯
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 06/21/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: salilda
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何在 Microsoft 團隊中使用內嵌翻譯。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2eb68a06a24436b6c12e4ee5b59a24a0da92ca7e
ms.sourcegitcommit: a6e44256c024fc3953cfd6a511ee024c4c7b8408
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/19/2019
ms.locfileid: "37047079"
---
<a name="turn-on-inline-message-translation-in-microsoft-teams"></a>開啟 Microsoft 團隊中的內嵌郵件翻譯 
=================================================

內嵌郵件翻譯是一種新的 Microsoft 團隊功能，可讓使用者將小組訊息轉換成由 Office 365 的個人語言設定所指定的[語言](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194)。

預設會針對您的組織推出內嵌郵件翻譯。 如果您想要允許使用者在團隊用戶端中使用這項功能，您必須開啟此設定。

> [!NOTE]
>此推出已從 office 365 政府社區版雲端和 Office 365 德國環境中的 Office 365 訂閱中排除。

## <a name="use-powershell-to-turn-on-inline-message-translation"></a>使用 PowerShell 開啟內聯郵件轉換

您可以使用訊息策略來開啟內嵌郵件翻譯。

使用[CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) Cmdlet 開啟原則。 原則需要幾分鐘的時間才能套用。 使用者可能需要登出並重新登入小組。

## <a name="use-the-microsoft-teams-admin-center-to-turn-on-inline-message-translation"></a>使用 Microsoft 團隊系統管理中心來開啟內嵌郵件翻譯

在**Microsoft 團隊系統管理中心**中，從左側導覽中選取 [**訊息原則**]，然後建立新的原則或編輯現有的原則，然後將 [**允許使用者將郵件翻譯**成] 選項設定為 [**開啟**]。

> [!NOTE]
> 此服務會進行翻譯並將它傳送給用戶端，而不會影響在合規性記錄中捕獲的內容。 若要深入瞭解翻譯，請參閱[什麼是 Microsoft Translator？](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)。