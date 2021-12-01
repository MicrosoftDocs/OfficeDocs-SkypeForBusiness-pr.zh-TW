---
title: 規劃接線連線會議
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.date: 10/28/2021
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
description: 深入瞭解運算子連線會議，例如需求與部署規劃。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: d910fd9d464d1c4ff452da70a3bde039e4748123
ms.sourcegitcommit: be8b820caf4b5a1a91ad444ba93da1df20bf63ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/01/2021
ms.locfileid: "61257514"
---
# <a name="plan-for-operator-connect-conferencing"></a>規劃接線連線會議

Microsoft 音訊會議提供撥入會議的能力，以及使用公用交換電話網路或 PSTN (電話) 撥出。  參與者使用Microsoft Teams會議橋接器加入會議。

使用運算子連線會議功能，組織可以使用協力廠商接線員的電話號碼加入Microsoft Teams會議。 如果您目前的接線員是 Microsoft Operator 連線程式的一部分，您可以將您的接線員的電話號碼新加到音訊會議橋接器，並使用這些電話號碼加入會議。

沒有運算子連線會議功能，組織只能使用 Microsoft 提供的電話號碼作為音訊會議橋接器。

>[!NOTE]
>本文將 Microsoft Operator 連線程式一部分的電話號碼提供者參照為「接線員」。
>
>若要查看您的運算子是否參與 Microsoft Operator 連線程式，請參閱 Microsoft 365運算子連線[目錄](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory)。

本文將說明運算子連線會議：

- [優點](#benefits)
- [授權需求與帳單](#licensing-requirements-and-billing)
- [Microsoft 音訊會議的其他資訊](#additional-information-on-microsoft-audio-conferencing)

有關設定會議連線運算子的資訊，請參閱設定連線[運算子](operator-connect-conferencing-configure.md)。

如果貴組織的部分使用者需要撥打 PSTN 電話號碼的外部電話，您仍然需要通話方案。 若要瞭解如何使用協力廠商運算子進行外部 PSTN 連接，請參閱規劃[運算子](operator-connect-plan.md)連線。

## <a name="benefits"></a>優點

會議連線運算子提供下列優點：

- **在接線員和 Microsoft 之間彈性地配置電話號碼。** 在 Microsoft 音訊會議標準訂閱 (使用來自 Microsoft 和您的接線員的電話號碼) ，或只會使用來自您的接線員 (的電話號碼，且只有 連線 會議授權) 。

- **運算子管理的基礎結構。**  您的運算子會管理 SBC (的會話邊界控制器) 與 Microsoft 的互連性，為您省去額外的硬體購買和管理。

- **更快速、更輕鬆地部署。**  從系統管理中心快速連接到您的接線員，並將電話號碼指派Teams橋接器。

- **增強的支援和可靠性。**  電信業者提供技術支援和共用服務等級協定以改善服務支援，而由 Azure 提供直接對等功能可建立一對一網路連接，提升可靠性。

如果連線，電話會議的運算子可能是適合貴組織的解決方案：

- 您想要保留 **與現有** 電話號碼提供者的合約

- 您想要擴大 **現有** Microsoft 音訊會議橋接器的全域涵蓋範圍

- 您想要從 **新的電話號碼** 提供者來源音訊會議的電話號碼

- **您的地理位置無法使用 Microsoft 音訊會議**

- 您想要 **使用每分鐘** 付費模式來運用音訊會議服務的接線員，例如使用免付費號碼，以及撥打 Teams 會議撥打到您訂閱中未包含之國家/地區的電話號碼

## <a name="licensing-requirements-and-billing"></a>授權需求與帳單

需要接線連線號碼才能加入他們組織的會議的使用者，必須指派 Microsoft 音訊會議標準訂閱或 microsoft Operator 連線 會議授權給他們。

### <a name="audio-conferencing-standard-subscription"></a>音訊會議標準訂閱

Microsoft 音訊會議標準訂閱可以購買為授權Microsoft Teams附加元件，並包含在 Microsoft 365 E5 Office 365 E5訂閱中。

音訊會議標準訂閱可讓訂閱者使用 Microsoft 的電話號碼，並擴充其音訊會議橋接器與來自接線員的電話號碼。 訂閱者也可以決定從會議Teams哪一個呼叫要透過 Microsoft 路由，以及哪些通話是透過接線員路由。

若要詳細資訊，請參閱 [**在會議連線運算子**](operator-connect-conferencing-configure.md)。

### <a name="operator-connect-conferencing-license"></a>接線連線會議授權

Microsoft Operator 連線會議授權可以取得為授權Microsoft Teams附加元件。

電信連線會議授權可讓訂閱者使用來自接線員的電話號碼，但不包含來自 Microsoft 的電話號碼。 所有來自會議Teams呼叫都必須經由接線員路由。

若要詳細資訊，請參閱 [**在會議連線運算子**](operator-connect-conferencing-configure.md)。

>[!Note]
>會議參與者不需要音訊會議標準訂閱授權或運算子 連線 會議授權，才能加入由具有電信連線會議功能的使用者所組織的會議。

使用 連線 會議，Microsoft 會依據貴組織所使用的音訊會議授權類型、Microsoft 音訊會議或接線員 連線 會議，以及 Microsoft 提供的任何電話號碼，向貴組織帳單。

您的接線員會向貴組織提出帳單，要求連線會議號碼。

## <a name="additional-information-on-microsoft-audio-conferencing"></a>Microsoft 音訊會議的其他資訊

Microsoft 音訊會議可讓參與者Microsoft Teams PSTN 電話號碼撥入，或撥出到 PSTN 電話號碼，以加入會議。 有關貴組織可用的 Microsoft 音訊會議功能詳細資訊，請參閱在[Microsoft 365。](audio-conferencing-in-office-365.md)
