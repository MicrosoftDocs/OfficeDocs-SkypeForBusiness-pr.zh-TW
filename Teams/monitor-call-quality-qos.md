---
title: 監控並改善 Microsoft 團隊的通話品質
author: lolajacobsen
ms.author: lolaj
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: vkorlep, siunies
description: 使用 [服務品質（QoS）] 設定，然後在 Microsoft 團隊中呼叫分析和通話品質儀表板。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2d5db11bbd9608aebb1eb2b73ebacc9793629e44
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085932"
---
# <a name="monitor-and-improve-call-quality-for-microsoft-teams"></a>監控並改善 Microsoft 團隊的通話品質

本文將介紹三個主要工具，您可以用來在 Microsoft 團隊中監控、排除、管理及改善通話品質。 

- **通話品質儀表板（CQD）**：若要分析整個組織的趨勢或問題，請推動效能的改善

- **通話分析**：分析個別使用者的通話與會議品質

- **服務品質（QoS）**：用於排定重要網路流量的優先順序



## <a name="monitor-and-troubleshoot-call-quality"></a>監控通話品質並進行疑難排解
您將會使用每個使用者的**通話分析**和**通話品質儀表板**，找出並疑難排解在進行中的作業時所產生的通話品質問題。 這可讓您提高整個網路的效能。 這兩種工具都是在團隊系統管理中心。

 - [**通話分析**] 會顯示與團隊中每位使用者的***特定通話與會議***相關的裝置、網路及連線性的詳細資訊。 團隊管理員和支援人員的代理程式會使用此資訊來針對特定通話中的通話品質和連線問題進行疑難排解。 若要深入瞭解，請參閱[設定通話分析](set-up-call-analytics.md)和[使用呼叫分析，以解決不佳通話品質的問題](use-call-analytics-to-troubleshoot-poor-call-quality.md)。
 
 - **通話品質儀表板（CQD）** 可在整個組織中提供通話品質的整個***網路視圖***。 使用 CQD 資訊來協助您找出並修正問題。 首先，[設定 CQD](turning-on-and-using-call-quality-dashboard.md)。 然後閱讀[團隊中的 [管理通話與會議品質](quality-of-experience-review-guide.md)]。

 呼叫分析與 CQD 會並存執行，而且可以獨立地或一起使用。 例如，如果通訊支援專家認為他們需要進一步協助解決使用者的呼叫問題，他們會將通話升級至通訊支援工程師，他們可以存取有關通話的其他資訊。 接著，通訊支援工程師會通知網路工程師，看看在通話分析中可能會注意到的與網站相關的問題。 網路工程師會檢查 CQD，以查看總體網站相關問題是否可能是造成使用者通話問題的原因。


## <a name="prioritize-important-network-traffic-using-qos"></a>使用 QoS 來設定重要網路流量的優先順序
當您的使用者開始使用團隊撥打電話與會議時，可能會遇到來電者的語音或撥打電話或會議。 共用影片可能會凍結或像素化，或完全失敗。 這是因為 IP 資料包所代表的語音和影片通信量遇到網路擁塞，而不是順序讀出或根本無法進行。 如果發生這種情況（或是要防止它在第一個位置發生），請使用**服務品質（QoS）**。 

透過 QoS，您可以將延遲敏感的網路流量（例如語音或視頻串流）劃分優先順序，讓它在不太敏感的流量（例如下載新的應用程式，需要額外的時間來下載，而不是大筆的情況下）中進行「在行中切削」。 QoS 會使用 Windows 群組原則物件和路由功能（稱為埠的存取控制清單）來識別及標記即時資料流中的所有資料包，這會指示您的網路為自己的私人網路絡頻寬提供語音、影片和螢幕共用。

在理想的情況下，您會在內部網路上實施 QoS，以準備好要推出小組，但您可以隨時進行。 如果您的小一點足夠小，您可能不需要 QoS。

當您準備好時，請參閱[在 Microsoft 團隊中實施服務品質（QoS）](QoS-in-Teams.md)。

若要使用 QoS 管理會議流量，請閱讀[設定您想要處理團隊會議即時媒體流量的方式](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)。


## <a name="related-topics"></a>相關主題

[設定通話分析](set-up-call-analytics.md)

[使用通話分析來疑難排解不良通話品質](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[設定 CQD](turning-on-and-using-call-quality-dashboard.md)

[在團隊中管理通話與會議品質](quality-of-experience-review-guide.md)

[Teams 疑難排解](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

