---
title: '資訊障礙和共用通道 (預覽) '
description: 本文說明 Microsoft Teams 中的資訊障礙如何支援共用頻道
author: robmazz
ms.author: robmazz
manager: laurawi
ms.reviewer: smahadevan
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- tier2
- purview-compliance
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: information-barriers
ms.openlocfilehash: 5b214a4c60df7b50f508fec7985c6f38b65985e6
ms.sourcegitcommit: 507e186972bcbc56c1547a1b9f357bfd38170b5a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/27/2022
ms.locfileid: "68047213"
---
# <a name="information-barriers-and-shared-channels-preview"></a>資訊障礙和共用通道 (預覽) 

Microsoft Teams 中的[共用頻道](shared-channels.md)會建立共同作業空間，讓您可以邀請不在團隊中的人員。 [Microsoft Purview 資訊障礙](/microsoft-365/compliance/information-barriers) 是可實作的原則，可限制並防止使用者和群組在組織內外彼此通訊。

在 Teams 中預設會啟用共用頻道。 您可以選擇人員是否可建立共用頻道、是否可以與組織外部人員共用，以及是否可建立頻道原則來參與外部共用頻道。 當貴組織設定資訊障礙原則時，會在設定共用通道時執行檢查，以確認所有現有通道成員和任何新增至共用通道的新使用者都違反資訊障礙原則條件。

請使用下表瞭解資訊障礙原則如何影響通訊，以及如何在設定共用頻道時產生特定行為：

|**案例**|**資訊障礙行為**|
|:-----------|:--------------------------------|
| **與組織中的使用者共用頻道** | 如果不允許使用者根據資訊障礙原則與共享頻道成員通訊，使用者就不會顯示在使用者搜尋中，且頻道不會與團隊共用。 <br><br> 如果無法依據資訊障礙原則新增使用者，您會看到下列訊息： *我們找不到任何相符專案。請洽詢您的 IT 系統管理員，討論如何擴大搜尋範圍。* |
| **與您擁有的另一個團隊共用貴組織中的頻道** | 如果其他團隊有任何使用者不允許根據資訊障礙原則與共享頻道成員通訊，則該頻道不會與團隊共用。 <br><br> 如果根據資訊障礙原則不允許通訊，您會看到下列訊息：頻道 *無法與此團隊共用。如需詳細資訊，請挑選另一個小組或連絡您的系統管理員。* |
| **與另一個您不擁有的團隊共用貴組織中的頻道** | 如果不允許團隊擁有者或其他團隊的任何使用者根據資訊障礙原則與共享頻道成員通訊，頻道就無法與團隊共用。 <br><br> 如果根據資訊障礙原則不允許通訊，您會看到下列訊息：頻道 *無法與此團隊共用。如需詳細資訊，請挑選另一個小組或連絡您的系統管理員。* |
| **當團隊與其他團隊共用頻道時，將新使用者新增至團隊** | 如果不允許新使用者根據資訊障礙原則與共享通道團隊的成員通訊，則無法將該使用者新增至團隊。 當您將使用者新增到擁有六個以上共用頻道的團隊時，系統會立即將該使用者新增到頻道，並支援共用功能。 如果發現新使用者不符合資訊障礙原則，則可能會停止小組和先前共用頻道的共用。<br><br> 如果無法依據資訊障礙原則新增使用者，您會看到下列訊息： *因資訊障礙原則而無法新增使用者。* |
| **與外部團隊共用頻道** | 內部和外部租使用者的資訊障礙原則不會限制不同租使用者使用者之間的通訊。 共用頻道可與外部使用者共用。 |
