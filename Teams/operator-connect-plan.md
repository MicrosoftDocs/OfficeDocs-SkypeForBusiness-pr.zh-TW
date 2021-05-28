---
title: 運算子連線
author: cazawideh
ms.author: czawideh
manager: serdars
ms.date: 04/12/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: 深入瞭解運算子連線，例如需求與部署規劃。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 088b36f546cebe67e10d840075e601e96a6df6e2
ms.sourcegitcommit: 39d26edd43b6066d5a6dee2a5ad1354a1e560a0d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694538"
---
# <a name="plan-for-operator-connect"></a>規劃運算子連線

>[!NOTE]
>運算子連線目前僅適用于公用 **預覽**。 公開預覽可讓您測試即將推出的功能，並提供意見回饋。 公用預覽中包含的功能可能不完整、可能會變更，且雲端版Office 365 政府版支援。

運算子連線是提供公用交換電話網絡與 PSTN (PSTN) 與Teams電話系統。  

本文將說明權益和需求，並列出參與運算子和連線運算子。  如果您決定運算子連線是貴組織正確的解決方案，請參閱閱讀本文後[，請參閱設定](operator-connect-configure.md)運算子連線。  

## <a name="benefits"></a>優點

使用運算子連線，如果您現有的接線員是 Microsoft Operator 連線 計畫的參與者，他們可以管理將 PSTN 通話Teams。 運算子連線計畫提供下列優點：

- **利用現有合約，或尋找新的運算子。** 您可以保留您偏好的運算子和合約，或從一系列參與的營運者中選擇新的，以滿足您的業務需求。

- **運算子管理的基礎結構。** 您的接線員會管理 PSTN 通話服務和會話邊界控制器 (SBC) ，讓您節省硬體購買和管理。

- **更快速、更輕鬆地部署。** 您可以快速連接到您的接線員，並將電話號碼指派給使用者 ---全部Teams系統管理中心。

- **增強的支援和可靠性。** 業者提供技術支援和共用服務等級協定以改善支援服務，而由 Azure 提供直接對等功能則建立一對一網路連接，以提高可靠性。

## <a name="requirements"></a>需求

 如果連線運算子或運算子，可能是適用于貴組織的解決方案：

- 您的地理位置無法提供 Microsoft 通話方案。
- 您偏好的運算子是 Microsoft Operator 連線參與者。
- 您想要尋找新的運算子，以在 Teams。

若要使用運算子連線電話號碼指派，請確定您的使用者為：

- Teams 電話授權。 若要深入瞭解，請參閱[什麼是電話系統？，Teams](what-is-phone-system-in-office-365.md)[指派附加元件授權給使用者](teams-add-on-licensing/assign-teams-add-on-licenses.md)。
- 在 TeamsOnly 模式中。 若要深入瞭解，[請參閱瞭解Microsoft Teams商務用 Skype及互通性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)。

## <a name="available-operators"></a>可用的運算子

下列運算子是 Microsoft Operator 連線參與者：

| 運算元 | 功能 | 國家/地區涵蓋範圍 |
| --- | --- | --- |
| `BT`  | 通話 | 比利時、丹麥、芬蘭、法國、德國、愛爾蘭、義大利、盧森堡、荷蘭、挪威、波蘭、南非、西班牙、瑞典、瑞士、英國 |
| `Intrado` | 通話 | 比利時、加拿大、丹麥、法國、德國、愛爾蘭、盧森堡、荷蘭、西班牙、瑞典、英國、美國  |
| `NTT`  | 通話 | 奧地利、比利時、巴西、加拿大、捷克、丹麥、芬蘭、法國、德國、愛爾蘭、義大利、盧森堡、墨西哥、荷蘭、挪威、波蘭、葡萄牙、波多黎各、羅馬尼亞、南非、西班牙、瑞典、瑞士、英國、美國 |
| `NuWave` | 通話 | 奧地利、比利時、加拿大、丹麥、法國、德國、愛爾蘭、義大利、荷蘭、葡萄牙、西班牙、瑞典、瑞士、英國、美國   |
| `Orange Business Services` | 通話 | 奧地利、比利時、捷克、丹麥、芬蘭、法國、法屬圭亞那、德國、哥德洛普、愛爾蘭、義大利、盧森堡、馬提克、馬約特、荷蘭、挪威、波蘭、葡萄牙、留尼翁、聖巴塞萊米、聖馬德、西班牙、斯瓦爾巴德、瑞典、瑞士、英國  |
| `Pure IP` | 通話 | 澳大利亞、奧地利、比利時、巴西、保加利亞、加拿大、智利、哥倫比亞、克羅地亞、賽普勒斯、捷克、丹麥、芬蘭、法國、德國、希臘、香港特別行政區、愛爾蘭、義大利、日本、立陶宛、盧森堡、馬來西亞、墨西哥、荷蘭、紐西蘭、挪威、巴薩、波蘭、葡萄牙、波多黎各、羅馬尼亞、新加坡、斯洛伐克、斯洛維尼亞、南非、西班牙、瑞典、瑞士、英國、美國  |
| `Rogers Business` | 通話 | 加拿大  |
| `TATA Communications` | 通話 | 澳大利亞、奧地利、比利時、加拿大、捷克、丹麥、法國、德國、香港特別行政區、匈牙利、愛爾蘭、義大利、馬來西亞、墨西哥、荷蘭、紐西蘭、波蘭、葡萄牙、羅馬尼亞、新加坡、韓國、西班牙、瑞典、瑞士、泰國、英國、美國 |
| `Telekom Deutschland` | 通話 | 德國  |
| `Telenor` | 通話 | 丹麥、芬蘭、挪威、瑞典  |
| `Verizon` | 通話 | 美國 |
