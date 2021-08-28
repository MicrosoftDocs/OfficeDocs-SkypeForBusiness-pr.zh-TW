---
title: 接聽自動回應和通話佇列通話
ms.reviewer: colongma
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: 說明雲端自動回應和通話佇列，並說明如何在 Teams。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: bb35bc5a035c03080ce44fa19fa3ecf5a5c674a6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580287"
---
# <a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a>直接從 Teams 回答自動語音應答和通話佇列的通話

Teams使用者可以直接從他們的用戶端接收和接聽來自雲端自動回應和Teams通話。

## <a name="what-are-auto-attendants-and-call-queues"></a>什麼是自動電話機和通話佇列？

雲端自動語音回應會提供一系列語音提示或音訊檔案，讓來電者在來電到組織時，聽到這些語音提示或音訊檔案，而不是由接線生聽到。 自動語音機可讓來電者透過功能表系統移動、撥打電話，或使用電話鍵台 (DTMF) 語音輸入來尋找使用者。

雲端通話佇列包括當某人來電到貴組織的電話號碼時所使用的問候語、自動保留通話的能力，以及搜尋下一個可用的通話代理程式來處理通話，而通話者正在聆聽保留的音樂。 您可以為貴組織建立單一或多個通話佇列。

## <a name="handling-an-auto-attendant-or-call-queue-call"></a>處理自動電話機或通話佇列通話

在接聽來電之前，使用者將能夠將來電與自動回應或通話佇列區別。 除了來電者的名稱和/或號碼外，每一個通話都會包含來電者嘗試與誰聯繫的資訊，為使用者提供更好的內容來稱呼來電者。

下圖顯示來自自動電話機或通話佇列的來電會如何顯示給使用者。

![來電通知的螢幕擷取畫面](media/answer-auto-attendant-and-call-queue-calls-image1.png)

一旦自動回應或通話佇列通話獲得接聽，使用者就可以像處理任何其他通話一樣處理&#x2014;他們可以在其他使用者中新增或召開會議，或將通話轉接給另一方。 此外，系統也會根據使用者的組配置來轉乘自動通話。

> [!NOTE] 
> 通話佇列通話不會根據使用者的組組進行轉轉。 這是為了確保來電者保留在佇列中，直到代理人可以接聽來電，且來電者不會意外轉轉。

> 代理人不會收到任何未接來電或來電佇列通話語音信箱的通知。

## <a name="supported-clients"></a>支援的用戶端

下列用戶端支援自動通話和通話佇列通話：

-    Microsoft Teams Windows 32 (64 位版本的用戶端) 
-    Microsoft TeamsMac 用戶端
-    Microsoft Teams iPhone應用程式
-    Microsoft TeamsAndroid 應用程式

系統Teams用戶端僅支援共同存在模式 ，Teams[唯一](/microsoftteams/setting-your-coexistence-and-upgrade-settings)。

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a>設定自動電話機和通話佇列支援Microsoft Teams

若要在 Microsoft Teams上接收自動話務和通話佇列通話，您必須設定互通性原則與升級原則。 請針對使用 Teams 與 商務用 Skype[的組織，檢查移](migration-interop-guidance-for-teams-with-skype.md)商務用 Skype。 如果您沒有設定自動電話機和/或通話佇列，並想這麼做，請參閱設定雲端 [自動](create-a-phone-system-auto-attendant.md) 電話機和 [建立雲端通話佇列](create-a-phone-system-call-queue.md)。

## <a name="known-issues"></a>已知問題

當通話佇列代理程式在行動裝置上接聽來電時，如果裝置已鎖定，通話可能會保持保留狀態。 使用者必須先解除鎖定裝置，然後接聽電話。


## <a name="related-topics"></a>相關主題

-    [電話系統或Microsoft 365 Office 365](what-is-phone-system-in-office-365.md)
-    [建立雲端通話佇列](create-a-phone-system-call-queue.md)
-    [什麼是雲端自動語音應答？](what-are-phone-system-auto-attendants.md)
-    [設定雲端自動語音應答](create-a-phone-system-auto-attendant.md)

