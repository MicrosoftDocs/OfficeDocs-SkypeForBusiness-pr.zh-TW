---
title: 接聽自動語音應答和通話佇列通話
ms.reviewer: colongma
author: DaniEASmith
ms.author: danismith
manager: serdars
audience: ITPro
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: 說明雲端自動語音應答和通話佇列，並說明如何在 Teams 中接聽這些電話。
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
ms.openlocfilehash: 1653f1a994da168126c06d10950c7db8e22e37c6
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614196"
---
# <a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a>直接從 Teams 回答自動語音應答和通話佇列的通話

Teams 使用者可以直接從 Teams 用戶端接收和接聽來自雲端自動語音應答和通話佇列的電話。

## <a name="what-are-auto-attendants-and-call-queues"></a>什麼是自動語音應答和通話佇列？

雲端自動語音應答會提供一系列語音提示或音訊檔案，來電者在撥入組織時會聽到來電者，而非使用者接聽。 自動語音應答可讓來電者在功能表系統中移動、撥打電話或尋找使用者，方法是使用電話鍵台 (DTMF) 或使用語音辨識的語音輸入。

雲端通話佇列包括當某人撥入貴組織的電話號碼時所使用的問候語、自動保留通話的功能，以及在通話者聆聽音樂時搜尋下一個可用來電代理程式處理通話的功能。 您可以為組織建立單一或多個通話佇列。

## <a name="handling-an-auto-attendant-or-call-queue-call"></a>處理自動語音應答或通話佇列通話

使用者在接聽電話之前，可以區分來電與自動語音應答或通話佇列的來電。 連同來電者的名稱和/或號碼，每個通話都會包含來電者嘗試連絡的相關資訊，讓使用者更清楚地瞭解如何接聽來電者。

下圖顯示自動語音應答或通話佇列的來電如何顯示給使用者。

![來電通知的螢幕擷取畫面。](media/answer-auto-attendant-and-call-queue-calls-image1.png)

一旦自動語音應答或通話佇列通話接聽後，使用者就可以像處理任何其他通話一樣處理通話&#x2014;他們可以在其他使用者中新增或會議，或將電話轉接到另一方。 此外，自動語音應答通話也會根據使用者的設定轉接。

> [!NOTE] 
> 通話佇列通話不會根據使用者的通話接聽規則設定轉接。 這是為了確保來電者維持在佇列中，直到專員可以接聽電話，而且不會意外轉接來電者為止。
>
> 從通話佇列接聽來電的使用者，只有在從 PSTN 提供來電者，或來電者的號碼符合目標使用者的本機小組用戶端連絡人時，才會顯示來電者的名稱。
>
> 專員不會收到任何未接來電或語音信箱的通知來電佇列通話。

## <a name="supported-clients"></a>支援的用戶端

下列用戶端支援自動語音應答和通話佇列通話：

-    Microsoft Teams Windows 用戶端 (32 和 64 位版本) 
-    Microsoft Teams Mac 用戶端
-    Microsoft Teams iPhone 應用程式
-    Microsoft Teams Android 應用程式

只有 Teams [共同存在模式](/microsoftteams/setting-your-coexistence-and-upgrade-settings)才支援 Teams 用戶端。

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a>設定 Microsoft Teams 的自動語音應答和通話佇列支援

若要在 Microsoft Teams 上接聽自動語音應答和通話佇列通話，您必須設定互通性原則和升級原則。 請檢閱[使用 Teams 與商務用 Skype的組織移轉和互通性](migration-interop-guidance-for-teams-with-skype.md)。 如果您沒有設定自動語音應答和/或通話佇列，並想要這樣做，請參閱 [設定雲端自動語音應答](create-a-phone-system-auto-attendant.md) 和 [建立雲端通話佇列](create-a-phone-system-call-queue.md)。

## <a name="known-issues"></a>已知問題

當通話佇列代理人在行動裝置上接聽來電時，如果裝置鎖定，通話可能會保留。 使用者必須先解除鎖定裝置，然後再接聽電話。


## <a name="related-topics"></a>相關主題

[建立雲端通話佇列](create-a-phone-system-call-queue.md)

[什麼是雲端自動語音應答？](what-are-phone-system-auto-attendants.md)

[設定雲端自動語音應答](create-a-phone-system-auto-attendant.md)

