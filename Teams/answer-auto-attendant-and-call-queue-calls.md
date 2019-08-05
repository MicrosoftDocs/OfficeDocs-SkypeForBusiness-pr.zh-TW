---
title: 直接從小組應答自動回應及呼叫佇列通話
ms.reviewer: waseemh
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: 描述雲端自動語音應答和通話佇列, 並說明您可以如何在團隊中回答這些通話。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 855029001863b6603548c865d5f7bfb039261a18
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/28/2019
ms.locfileid: "36183840"
---
<a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a>直接從小組應答自動回應及呼叫佇列通話
===========================================================

團隊使用者可以從雲端自動語音應答並直接從其小組用戶端呼叫佇列來接收和接聽通話。 針對團隊使用者, 現在可以使用自動語音應答功能, 而且通話佇列功能是在預覽中。 

## <a name="what-are-auto-attendants-and-call-queues"></a>什麼是自動語音應答及呼叫佇列？

雲端自動語音應答提供一系列的語音提示或音訊檔案, 當來電者撥入組織時, 會聽到該語音提示, 而不是人工操作員。 自動接聽: 可讓呼叫者透過功能表系統、撥打電話或使用語音辨識來尋找使用者 (使用電話鍵台 (DTMF) 或語音輸入。

雲端通話佇列包括某人撥入您組織的電話號碼時所使用的問候語、自動保留通話的功能, 以及在通話時搜尋下一個可用的呼叫代理程式來處理通話的功能在暫停時聆聽音樂。 您可以為組織建立單一或多個通話佇列。

## <a name="handling-an-auto-attendant-or-call-queue-call"></a>處理自動語音應答或通話佇列通話

使用者將能夠在來電前, 在自動語音應答或通話佇列中區別來電。 隨著來電者的名稱和/或數位, 每次呼叫都會包含來電者嘗試到達者的資訊, 為使用者提供更好的方式來解決來電者。

下圖顯示如何將來自自動語音應答或通話佇列的本機號碼給使用者。

![來電通知的螢幕擷取畫面](media/answer-auto-attendant-and-call-queue-calls-image1.png)

當您接聽自動語音應答或通話佇列呼叫之後, 使用者就可以像處理任何其他通話一樣處理呼叫, &#x2014; 他們可以在其他使用者中新增或會議, 或將來電轉接至另一方。 此外, 自動來電呼叫將根據使用者的設定來轉寄。

> [!NOTE] 
> 通話佇列通話不會根據使用者的設定來轉寄。 這是為了確保呼叫者保留在佇列中, 直到工程師可以接聽通話且來電者不會被意外轉寄。

## <a name="supported-clients"></a>支援的用戶端

在下列用戶端提供自動語音應答及呼叫佇列呼叫支援:

-   Microsoft 團隊 Windows 用戶端 (32 和64位版本)
-   Microsoft 團隊 Mac 用戶端
-   Microsoft 團隊 iPhone 應用程式
-   Microsoft 團隊 Android 應用程式

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a>針對 Microsoft 團隊設定自動語音應答及呼叫佇列支援

若要在 Microsoft 團隊中接收自動語音應答及呼叫佇列通話, 您必須設定您的互通性原則和升級原則。 請參閱[與商務用 Skype 搭配使用團隊之組織的遷移與互通性](migration-interop-guidance-for-teams-with-skype.md)。 如果您沒有設定自動語音應答及/或通話佇列, 請參閱[設定雲端自動](create-a-phone-system-auto-attendant.md)語音應答及[建立雲端通話佇列](create-a-phone-system-call-queue.md)。

## <a name="related-topics"></a>相關主題

-   [什麼是 Office 365 中的電話系統](what-is-phone-system-in-office-365.md)
-   [建立雲端通話佇列](create-a-phone-system-call-queue.md)
-   [什麼是雲端自動語音應答？](what-are-phone-system-auto-attendants.md)
-   [設定雲端自動語音應答](create-a-phone-system-auto-attendant.md)

