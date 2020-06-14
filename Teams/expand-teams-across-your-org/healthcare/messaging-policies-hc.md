---
title: 醫療保健組織的安全訊息
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: 瞭解如何自訂可包含讀信回條及優先順序通知的安全訊息原則。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b4bd8032cce78e388d221108ebdfc08a16b8afd1
ms.sourcegitcommit: 5dff3217760cf881d1d96e5d5c76101c90afcbc0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/12/2020
ms.locfileid: "44724888"
---
# <a name="get-started-with-secure-messaging-for-healthcare-organizations"></a>開始使用適用於醫療保健組織的 Secure Messaging

郵件服務原則是用來控制 Microsoft 團隊使用者可以使用的聊天和通道訊息功能，而且是整個部署安全訊息（例如醫院、診所或醫生的辦公室），在這種情況下，無論閱讀重要訊息的時間為何，都能及時挑選並採取行動。

您可以使用全域（組織範圍預設值）原則，或針對貴組織中的人員建立一或多個自訂的訊息原則。 除非您建立並指派自訂原則，否則貴組織中的使用者將會自動取得全域原則。 在您建立自訂原則之後，請指派給它一個使用者或貴組織中的一組使用者。 例如，您可以選擇只允許特定工作角色使用這些功能（例如醫生和護士）及其他工人（例如 janitorial 或廚房教職員），以取得更有限的功能集。 自己決定貴組織的需求為何，以下是最常提出的建議。

您可以使用系統管理員認證登入，然後在左側流覽窗格中選擇 [**訊息原則**]，輕鬆地在[Microsoft [小組管理中心](https://admin.teams.microsoft.com)] 中管理原則。

 ![[訊息原則] 頁面的螢幕擷取畫面](../../media/hc-messaging-policy-admin-center.png)

若要編輯貴組織的現有預設訊息原則，請按一下 [**全域（組織範圍預設值）**]，然後進行您要的變更。 若要建立新的自訂訊息原則，**請按一下 [新增]** ，然後選取您的設定。 完成後，請選擇 [**儲存**]。

![[訊息原則] 設定的螢幕擷取畫面](../../media/hc-messaging-policy.png)

下列設定對於醫療保健應用程式是特別重要的，在設計 [保健] 欄位中使用的自訂原則時，應該考慮以下設定：

## <a name="read-receipts"></a>讀信回條

[已讀] 回執可讓聊天訊息的寄件者知道其郵件已由1:1 和群組聊天20個人或較少的收件者閱讀。 使用此設定來指定讀信回條是由使用者控制、針對所有人開啟，或針對所有人關閉。 在醫療保健組織中，郵件讀信回條很重要，因為他們移除郵件是否已讀取的 uncertainly。

針對醫療保健應用程式，請選擇 [**由使用者控制**] 或 [**針對所有人**]。 請注意，為整個租**使用者**設定回執的唯一方式，就是只針對整個租使用者（名為「全域（組織範圍的預設值）」的預設原則），或在租使用者中的所有訊息原則都使用相同的收據設定。 當**針對所有人**啟用此功能時，[已讀] 的 [已讀] 功能最有效。

*沒有讀信回條的用法範例：* Jakob Roth （高風險患者）可獲准在醫院中。Sofia Krause 是一個護士，共同作業是共同作業（IDT）的醫療人員小組（），其中包括不同的專家，都是指派給本患者的主要護理協調員。  Sofia 會將電子郵件及其他立即訊息傳送給使用各種訊息用戶端和應用程式的護士和醫生群組，而且通常不會收到任何回應，也不會指出郵件是否由小組成員閱讀。 由於 tangled 通訊流程，Jakob 的藥物是 misapplied，而他的醫院仍在延伸。

已*讀回執的用法範例：* Jakob Roth （高風險患者）可獲准在醫院中。Sofia Krause 是一個護士，共同作業是共同作業（IDT）的醫療人員小組（），其中包括不同的專家，都是指派給本患者的主要護理協調員。  Sofia 會使用一組醫生和其他醫護人員來啟動群組聊天，他們將與患者共同合作，並開始緊急會審。在整個護理協調流程中，護士與醫生透過患者的護理方案進行溝通並共同作業。  重要及緊急訊息是透過1:1 和群組聊天交談傳送。 Sofia 會使用 [已讀] 回執功能來判斷傳送給要求支援的訊息是否由目標醫生或護士提供並閱讀。 Jakob 的患者成果接近最佳，而且因為他的護理小組能順暢地順利進行。

## <a name="send-urgent-messages-using-priority-notifications"></a>使用優先順序通知傳送緊急郵件

當您傳送聊天訊息給其他使用者時，使用者可以將郵件標示為*緊急*。 這項功能可協助醫院人員在重要事件需要注意時提醒對方。 與一般*重要*的郵件不同，[優先順序通知](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462)會在長達20分鐘的時間內通知使用者，或直到收件者挑選郵件並進行閱讀為止，以及時的方式最大限度地處理郵件的可能性。

系統管理員可以啟用或停用指派此原則的使用者傳送優先順序通知的能力。 此功能預設為開啟。 [優先順序] 訊息的收件者可能不具備相同的訊息原則，也不會有停用接收優先順序訊息的選項。 針對醫療保健應用程式，我們建議您至少為部分使用者啟用該功能，但您必須決定這些使用者。

*用法範例：* Sofia Krause 是 readmitting 高風險患者，Jakob Roth。 Manuela Carstens （一個醫師）是這種患者的主要護理醫生。  Sofia 會使用優先順序通知來傳送訊息給 Manuela，詢問 Jakob 的會審的立即協助。  Manuela 的手機會接收郵件，但 Manuela 不會覺得手機震動且無法回復。 小組會重新通知 Manuela，並持續再次提醒，直到她讀取該郵件。 如果已啟用 [已讀] 回執，Sofia 可以知道郵件已由 Manuela 讀取，即使 Manuela 決定如何回應也一樣。

## <a name="related-topics"></a>相關主題

- [管理小組中的訊息傳遞原則](../../messaging-policies-in-teams.md)
- [開始使用適用於醫療保健組織的 Teams](teams-in-hc.md)
