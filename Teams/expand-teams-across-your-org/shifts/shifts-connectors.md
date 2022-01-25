---
title: 移轉連接器
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解 Shifts 連接器，以及如何使用這些連接器將 Shifts 連接到您的員工管理系統。
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7a5e330710fcbdbda6c82db2643e1ed7c0fa5a26
ms.sourcegitcommit: 9ef6e36eeba7db70971f4eb1a45f0ded394b1fe6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2022
ms.locfileid: "62192478"
---
# <a name="shifts-connectors"></a>移轉連接器

## <a name="overview"></a>概觀

Shifts 連接器可讓您將 Shifts 整合為 Microsoft Teams 中的排程管理工具，以及您的員工管理 (WFM) 系統。 設定連接之後，前線工作人員可以在 Shifts 中順暢地在 WFM 系統中查看及管理排程。

將 WFM 系統與Teams讓前線員工能更有效地管理排程，並簡化日常程式，提升參與度與生產力。 前線員工有一個排程、通訊和共同作業的地方，可以隨時隨地在任何裝置上完成工作。

我們提供受管理且開放來源的 Shifts 連接器。 本文提供 Shifts 連接器及其工作方式概觀。

## <a name="how-shifts-connectors-work"></a>Shifts 連接器如何工作

連接器會同步處理您的 WFM 系統與 Shifts 之間的排程資料，將貴組織的排程納入Teams。 輪班是前線員工為了排程需求而參與的地方。 您的 WFM 系統是商務規則、合規性和智慧的記錄系統。

資料透過連接器流動，這兩種方式可確保排程一直為最新狀態。 您的 WFM 系統排程會同步到 Shifts。 此外，在 Shifts 中對排程進行變更會即時同步到您的 WFM 系統。 做為記錄系統，所有商務規則都是由您的 WFM 系統強制執行，然後再將資料儲存到 Shifts。

## <a name="managed-shifts-connectors"></a>受管理的 Shifts 連接器

受管理的 Shifts 連接器是一種與合作夥伴共同開發的連接器。 受管理的連接器是由我們或我們的合作夥伴託管和管理。 使用受管理的連接器時，只需要極少的設定。

### <a name="reflexis-shifts-connector-for-microsoft-teams"></a>適用于 Microsoft Teams

適用于 Microsoft Teams 的 Reflexis Shifts 連接器是由斑馬系統託管和管理。 有了這個連接器，您可以將 Shifts 與 Reflexis WFM 系統整合，以管理您的排程，並保持其最新狀態。

前線員工可存取 Teams 中的班次排程，而且他們的要求會從 Shifts 同步處理至RWS (RWS) 。 在 RWS 中建立的要求和班次狀態會同步處理至 Teams。

:::image type="content" source="../../media/shifts-connector-reflexis.png" alt-text="螢幕擷取畫面顯示行動裝置上的班次清單，以及一份在 Reflexis 中排程的螢幕擷取畫面" lightbox="../../media/shifts-connector-reflexis.png":::

前線管理員可以：

- 在 Reflexis 中發佈班和排程，然後以 Shifts 來查看。
- 在反射和 Shift 中編輯班次。
- 在反射和班次中建立、管理及指派已開啟的班。
- 在自反式和班次中，查看及核准員工提出的排程要求。

前線工作人員可以：

- 在 Shifts 中查看自己的班及其小組的班和排程。
- 要求請假、開啟班次，以及調班，並提供班次。

若要深入瞭解，請前往 https://connect.zebra.com/microsoft-connectors 。

## <a name="open-source-shifts-connectors"></a>開放來源 Shifts 連接器

開放來源 Shifts 連接器是社群導向的整合，建立在[Shifts Graph API 上](/graph/api/resources/shift)。 下列開放來源連接器可供使用：

- Kronos-to-Teams WFC 內部部署
- 適用于 Blue Yonder (2017 至 2020.2 (的 JDA-to-Teams Shifts 連接器) 

每個連接器都隨附詳細的部署和組組指南。 其中包括 Azure Resource Manager (ARM) 部署腳本，讓您在 Microsoft Azure 中託管所有必要的Microsoft Azure。 原始程式碼和部署腳本可在文件庫中GitHub[下載](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors)。 您可以根據需求進行部署或自訂或擴充。

若要深入瞭解，請參閱 [生產就緒的 Shifts 連接器](/microsoftteams/platform/samples/shifts-wfm-connectors)。

## <a name="related-articles"></a>相關文章

- [管理 Shifts 應用程式](manage-the-shifts-app-for-your-organization-in-teams.md)
