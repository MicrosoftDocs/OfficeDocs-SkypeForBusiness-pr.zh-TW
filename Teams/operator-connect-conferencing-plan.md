---
title: 規劃電信業者連線會議
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
description: 深入瞭解電信業者連線會議，例如部署需求和規劃。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 881df7d9bd2d2d2bcbf6775654a97066a2927250
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676015"
---
# <a name="plan-for-operator-connect-conferencing"></a>規劃電信業者連線會議

Microsoft 音訊會議提供使用公用交換電話網 (PSTN) 電話號碼撥入會議及從會議撥出的功能。  參與者使用音訊專用會議橋接器加入Microsoft Teams會議。

透過電信業者連線會議功能，組織可以使用協力廠商電信業者的電話號碼來加入Microsoft Teams會議。 如果您目前的電信業者是 Microsoft 電信業者連線 計畫的一部分，您可以將電信業者的電話號碼新增至音訊會議橋接器，並使用這些號碼加入會議。

如果沒有電信業者連線會議功能，組織只能將 Microsoft 提供的電話號碼用於音訊會議橋接器。

>[!NOTE]
>本文將參照屬於 Microsoft 電信業者連線 計畫的電話號碼提供者做為「運算子」。
>
>若要查看您的電信業者是否參與 Microsoft 電信業者連線 計畫，請參[閱Microsoft 365 電信業者連線目錄](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory)。

本文將說明電信業者連線會議：

- [優點](#benefits)
- [授權需求與帳單](#licensing-requirements-and-billing)
- [Microsoft 音訊會議 的其他資訊](#additional-information-on-microsoft-audio-conferencing)

如需設定電信業者連線會議的相關資訊，請參閱設定[電信業者連線會議](operator-connect-conferencing-configure.md)。

如果貴組織的某些使用者需要撥打 PSTN 電話號碼的外部電話，您仍需要通話方案。 若要瞭解如何使用協力廠商運算子進行外部 PSTN 連線，請參閱[規劃電信業者連線](operator-connect-plan.md)。

## <a name="benefits"></a>優點

電信業者連線會議提供下列優點：

- **在您的電信業者和 Microsoft 之間彈性配置電話號碼。** 僅) 搭配 Microsoft 音訊會議 Standard 訂閱使用 Microsoft 和電信業者 (的電話號碼，或僅) 使用您電信業 電信業者連線會議者 (的電話號碼。

- **由運算子管理的基礎結構。** 您的運算子會管理會話框線控制器 (SBC) 以及與 Microsoft 的互連性，讓您省下額外硬體購買與管理費用。

- **更快速、更容易部署。** 從Teams系統管理中心快速連線到您的電信業者，並將電話號碼指派到音訊會議橋接器。

- **增強的支援與可靠性。** 電信業者提供技術支援和共用服務等級協定，以改善服務支援，而由 Azure 提供的直接對等會建立一對一網路連線以增強可靠性。

電信業者連線會議下列情況可能是您組織的正確解決方案：

- 您想要保留與現有電話號碼提供者的 **合約**

- 您想要擴充現有 Microsoft 音訊會議橋接器的 **全球涵蓋範圍**

- 您想要從新的電話號碼提供者 **為音訊會議來源** 電話號碼

- **您的地理位置無法使用 Microsoft 音訊會議**

- 您想要 **利用電信業者以每分鐘付費模式來音訊會議服務**，例如使用免付費電話號碼，以及從Teams會議撥出到訂閱中未包含之國家/地區的電話號碼

## <a name="licensing-requirements-and-billing"></a>授權需求與帳單

需要電信業者連線會議號碼才能加入其所召集會議的使用者，必須擁有 Microsoft 音訊會議 標準版訂閱或 Microsoft 電信業者連線會議授權。

### <a name="audio-conferencing-standard-subscription"></a>音訊會議標準版訂閱

Microsoft 音訊會議 標準版訂閱可做為Microsoft Teams授權的附加元件購買，也包含在Microsoft 365 E5和Office 365 E5訂閱中。

音訊會議標準版訂閱可讓訂閱者使用 Microsoft 的電話號碼，並利用電信業者的號碼擴充其音訊會議橋接器。 訂閱者也可以決定要透過 Microsoft 路由Teams會議的撥出電話，以及要透過電信業者路由哪些來電。

如需詳細資訊，請參閱 [**設定電信業者連線會議**](operator-connect-conferencing-configure.md)。

### <a name="operator-connect-conferencing-license"></a>電信業者連線會議授權

Microsoft 電信業者連線會議授權可以當做Microsoft Teams授權的附加元件取得。

電信業者連線會議授權可讓訂閱者使用電信業者的電話號碼，但不包括 Microsoft 的電話號碼。 所有來自Teams會議的撥出電話都必須透過電信業者路由。

如需詳細資訊，請參閱 [**設定電信業者連線會議**](operator-connect-conferencing-configure.md)。

>[!Note]
>會議參與者不需要音訊會議標準訂閱授權或電信業者連線會議授權，即可加入由具有電信業者連線會議功能的使用者召集的會議。

使用電信業者連線會議，Microsoft 會根據貴組織、Microsoft 音訊會議或電信業者連線會議使用的音訊會議授權類型，以及 Microsoft 所提供之任何電話號碼的使用方式，向貴組織帳單。

您的電信業者會向貴組織請款，要求其使用所提供的電信業者連線會議號碼。

## <a name="additional-information-on-microsoft-audio-conferencing"></a>Microsoft 音訊會議 的其他資訊

Microsoft 音訊會議可讓參與者使用 PSTN 電話號碼或撥出 PSTN 電話號碼來加入Microsoft Teams會議。 如需貴組織可用之 Microsoft 音訊會議 功能的詳細資訊，請參[閱Microsoft 365中的音訊會議](audio-conferencing-in-office-365.md)。
