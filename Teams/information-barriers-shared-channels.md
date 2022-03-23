---
title: '資訊障礙和共用頻道 (預覽) '
description: 本文說明如何在共用通道中Microsoft Teams資訊障礙
author: robmazz
ms.author: robmazz
manager: laurawi
ms.reviewer: smahadevan
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: information-barriers
ms.openlocfilehash: c65da8b9b04296a7377f29aead811e1efcfb4048
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/22/2022
ms.locfileid: "63712118"
---
# <a name="information-barriers-and-shared-channels-preview"></a>資訊障礙和共用頻道 (預覽) 

[共用頻道](shared-channels.md)Microsoft Teams建立共同合作空間，您可以在這裡邀請不在團隊中的人員。 [資訊障礙](/microsoft-365/compliance/information-barriers) 是可執行以限制及防止使用者和群組在貴組織內外彼此通訊的政策。

共用頻道預設在 Teams。 您可以選擇人員是否可建立共用頻道、是否可以與組織外部人員共用，以及是否可建立頻道策略參與外部共用頻道。 當您組織中已配置資訊障礙原則時，會執行檢查以在組組共用通道時，確認現有通道成員和新使用者都未違反資訊障礙原則條件。

使用下表瞭解資訊隔障政策如何影響通訊，以及在配置共用通道時會導致特定行為：

|**案例**|**資訊障礙行為**|
|:-----------|:--------------------------------|
| **與貴組織的使用者共用頻道** | 如果根據資訊障礙政策，不允許使用者與共享頻道成員通訊，使用者不會顯示在使用者搜尋中，且頻道不會與小組共用。 <br><br> 如果無法根據資訊障礙政策新增使用者，會看到下列訊息：找不到 *任何符合專案。請詢問您的 IT 系統管理員，以擴大搜尋範圍。* |
| **與您擁有的另一個小組共用貴組織的頻道** | 如果另一個小組有不允許根據資訊障礙政策與共享頻道成員通訊的任何使用者，則頻道不會與小組共用。 <br><br> 如果根據資訊障礙政策不允許通訊，則會看到下列訊息：頻道無法與這個 *小組共用。選擇另一個小組或與您的系統管理員聯繫以瞭解更多資訊。* |
| **與另一個您不擁有的團隊共用貴組織的頻道** | 如果團隊擁有者或其他團隊的任何使用者無法根據資訊障礙政策與共享頻道成員通訊，則頻道無法與小組共用。 <br><br> 如果根據資訊障礙政策不允許通訊，則會看到下列訊息：頻道無法與這個 *小組共用。選擇另一個小組或與您的系統管理員聯繫以瞭解更多資訊。* |
| **當團隊與其他團隊共用頻道時，新增使用者至團隊** | 如果根據資訊障礙政策，不允許新使用者與共享頻道小組成員通訊，則使用者無法新加入團隊。 當您將使用者新增到擁有六個或多個共用頻道的團隊時，該使用者會立即新加入頻道，且支援共用。 如果發現新使用者不符合資訊障礙政策，小組和先前共用頻道的共用可能會停止。<br><br> 如果無法根據資訊障礙政策新增使用者，會看到下列訊息：由於資訊障礙政策，無法 *新增使用者。* |
| **與外部小組共用頻道** | 內部和外部租使用者的資訊隔離政策不會限制不同租使用者的使用者之間的通訊。 共用頻道可供與外部使用者共用。 |
