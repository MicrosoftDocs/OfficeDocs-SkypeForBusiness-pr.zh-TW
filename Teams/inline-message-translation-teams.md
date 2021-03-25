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
<a name="turn-off-inline-message-translation-in-microsoft-teams"></a>在 Microsoft Teams 中關閉內嵌郵件翻譯
=================================================

內嵌郵件翻譯是 Microsoft Teams 功能，可讓使用者將 Teams[](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194)郵件翻譯成其個人語言設定所指定的語言。

內嵌郵件翻譯預設適用于貴組織。 如果您想要允許使用者在 Teams 用戶端內使用此功能，就不需要進行變更。

> [!NOTE]
>在我們的 Office 365 政府社群雲端和 Office 365 Germany 環境中，這項推出方案不包含 Office 365 訂閱。

## <a name="use-powershell-to-turn-off-inline-message-translation"></a>使用 PowerShell 關閉內嵌郵件翻譯

您可以使用訊息策略關閉內嵌郵件翻譯。

使用 [Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) Cmdlet 關閉該策略。 原則需要幾分鐘的時間才能適用。 使用者可能需要登出並重新登錄 Teams。

## <a name="use-the-microsoft-teams-admin-center-to-turn-off-inline-message-translation"></a>使用 Microsoft Teams 系統管理中心關閉內嵌郵件翻譯

在 **Microsoft Teams 系統** 管理中心，從左側流覽選取訊息策略，然後建立新策略或編輯現有的策略，然後將郵件翻譯選項設為 **關閉**。

> [!NOTE]
> 服務會進行翻譯，並傳送給用戶端，且對合規性記錄中捕獲的內容沒有影響。 若要深入瞭解翻譯，請參閱什麼是 [Microsoft Translator？](/azure/cognitive-services/translator/translator-info-overview)