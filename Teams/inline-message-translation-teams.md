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
ms.openlocfilehash: 391814e9197ebcf4839adac35dc2a8b96085b545
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2020
ms.locfileid: "44638512"
---
<a name="turn-on-inline-message-translation-in-microsoft-teams"></a>開啟 Microsoft 團隊中的內嵌郵件翻譯 
=================================================

內嵌郵件翻譯是一種新的 Microsoft 團隊功能，可讓使用者將小組訊息轉換成其個人語言設定所指定的[語言](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194)。

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