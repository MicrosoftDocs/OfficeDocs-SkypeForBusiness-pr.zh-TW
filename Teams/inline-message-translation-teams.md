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
ms.openlocfilehash: 719f97e72f099edb4d14c22ef9d5a3de0f787ea7411f42f1d777ea842bcc4e27
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54339641"
---
# <a name="turn-off-inline-message-translation-in-microsoft-teams"></a>在郵件中關閉內嵌郵件翻譯Microsoft Teams

內嵌郵件翻譯是一項Microsoft Teams功能，可讓使用者將Teams訊息翻譯成其個人語言設定[](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194)所指定的語言。

根據預設，貴組織會推出內嵌郵件翻譯。 如果您想要允許使用者在用戶端內使用這項功能，Teams變更。

> [!NOTE]
>在我們的雲端和德國Office 365訂閱中Office 365 政府版 Community這項Office 365推出。

## <a name="use-powershell-to-turn-off-inline-message-translation"></a>使用 PowerShell 關閉內嵌郵件翻譯

您可以使用訊息策略關閉內嵌郵件翻譯。

使用 [Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) Cmdlet 關閉該策略。 原則需要幾分鐘的時間才能適用。 使用者可能需要登出並重新Teams。

## <a name="use-the-microsoft-teams-admin-center-to-turn-off-inline-message-translation"></a>使用 Microsoft Teams系統管理中心關閉內嵌郵件翻譯

在 **Microsoft Teams系統** 管理中心中，從左側流覽選取訊息策略，然後建立新策略或編輯現有的策略，然後將郵件選項設為 **關閉**。 

> [!NOTE]
> 服務會進行翻譯，並傳送給用戶端，且對合規性記錄中捕獲的內容沒有影響。 若要深入瞭解翻譯，請參閱[翻譯Microsoft 翻譯工具？](/azure/cognitive-services/translator/translator-info-overview)