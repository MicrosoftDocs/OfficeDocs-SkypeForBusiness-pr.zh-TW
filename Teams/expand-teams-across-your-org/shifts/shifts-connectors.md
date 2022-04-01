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
ms.openlocfilehash: 930f4b7a311acc7c34e60b7916071d10349c0313
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/31/2022
ms.locfileid: "64592888"
---
# <a name="shifts-connectors"></a>移轉連接器

## <a name="overview"></a>概觀

Shifts 連接器可讓您將 Shifts 整合為 Microsoft Teams 中的排程管理工具，與您的員工管理 (WFM) 系統。 設定連接之後，前線工作人員可以在 Shifts 中順暢地在 WFM 系統中查看及管理排程。

將 WFM 系統與Teams讓前線員工能更有效地管理排程，並簡化日常程式，提升參與度與生產力。 前線員工有一個排程、通訊和共同作業的地方，可以隨時隨地在任何裝置上完成工作。

我們提供受管理且開放來源的 Shifts 連接器。 本文提供 Shifts 連接器及其工作方式概觀。

## <a name="how-shifts-connectors-work"></a>Shifts 連接器如何工作

連接器會同步處理您的 WFM 系統與 Shifts 之間的排程資料，將貴組織的排程納入Teams。 輪班是前線員工為了排程需求而參與的地方。 您的 WFM 系統是商務規則、合規性和智慧的記錄系統。

資料透過連接器流動，這兩種方式可確保排程一直為最新狀態。 您的 WFM 系統排程會同步到 Shifts。 此外，在 Shifts 中對排程進行變更會即時同步到您的 WFM 系統。 做為記錄系統，所有商務規則都是由您的 WFM 系統強制執行，然後再將資料儲存到 Shifts。

## <a name="managed-shifts-connectors"></a>受管理的 Shifts 連接器

受管理的 Shifts 連接器是一種與合作夥伴共同開發的連接器。 受管理的連接器是由我們或我們的合作夥伴託管和管理。 使用受管理的連接器時，只需要極少的設定。

### <a name="microsoft-teams-shifts-connector-for-blue-yonder"></a>Microsoft Teams藍色 Yonder 的 Shifts 連接器
<a name="blue_yonder"> </a>

Blue Yonder Teams Shifts 連接器是由 Microsoft 託管和管理的第一方產品。 有了這個連接器，您可以將 Shifts 與 Blue Yonder 員工管理 (Blue Yonder WFM) 版本 2020.3、2021.1 或 2021.2 整合，以管理您的排程並保持最新狀態。  

> [!NOTE]
> 如果您有 Blue Yonder WFM 版本 2020.3 或 2021.1，請適用 2020.3.0.4 或 2021.1.0.3 修補程式。 此修補程式可修正使用者在 Shifts 中收到永久錯誤訊息的問題。 它也修正了使用者無法更新 Shifts 中的可用性的問題。

:::image type="content" source="../../media/shifts-connector-blue-yonder.png" alt-text="螢幕擷取畫面顯示行動裝置上 Shifts 中的調班要求、在桌面Teams中要求核准，以及 Blue Yonder WFM 中的排程。" lightbox="../../media/shifts-connector-blue-yonder.png":::

前線管理員可以：

- 在 Blue Yonder WFM 中發佈班次和排程，然後以 Shifts 來查看。
- 在 Blue Yonder WFM 中建立、管理及指派已開啟的班，然後以 Shifts 來查看。
- 在 Shifts 中指派在 Blue Yonder WFM 中建立開啟的班。
- 在藍色 Yonder WFM 中建立、編輯及刪除假，並查看 Shifts。
- 在 Blue Yonder WFM 和 Shifts 中，查看及核准來自員工排程要求。
- 在 Blue Yonder WFM 中設定及更新員工可用性，並查看 Shifts。

前線工作人員可以：

- 在 Shifts 中查看自己的班及其小組的班和排程。
- 在 Shifts 中要求請假、開啟班和調班。
- 在 Shifts 中設定其可用性。

目前不支援下列動作：

- 在 Shifts 中新增、編輯、刪除、儲存或發佈班次。
- 在 Shifts 中新增、編輯、刪除、儲存或發佈假。
- 在 Shifts 中新增、編輯、刪除、儲存或發佈已開啟的班。

當前線主管或工作人員嘗試在 Shifts 中執行這些動作時，他們會收到一則訊息，告知他們不支援該動作。

#### <a name="example-scenario"></a>範例案例

主管 Eden 在 Blue Yonder WFM 中發佈排程，此排程會透過連接器同步Teams Shifts。 Alex 是教職員成員，Teams裝置上收到通知，並查看他的排程和指派的班。

Alex 需要休息一段時間，然後使用 Shifts 要求休息一天。 要求會透過連接器即時送到 Blue Yonder WFM。 Blue Yonder WFM 可確保要求符合商務規則，並建立要求。 Eden 在 Blue Yonder WFM 中查看並核准要求，且核准會同步處理Teams。  (Eden 也可以查看並核准 Shifts) 。 Alex 會收到通知Teams他的要求已獲核准，並查看他更新的排程。

Alex 想要與同事調班。 在 Shifts 中，Alex 會根據 Blue Yonder WFM 中的商務規則，查看所有符合調班資格的班清單。 Alex 會選擇目前指派給 Gena 的班。 Gena 會Teams裝置上的通知，並接受調換要求。 Eden 會查看並核准 Shifts 中的要求，且核准會同步處理至 Blue Yonder WFM。  (Eden 也可以查看並核准 Blue Yonder WFM) 。 Alex 和 Gena 會Teams，並查看其更新的排程。

#### <a name="set-up-a-connection"></a>設定連接

使用連接器將 Shifts 與 Blue Yonder WFM 整合只需要幾個步驟。 您可以使用工作介面中的 Shifts 連接器精靈Microsoft 365 系統管理中心快速設定連接。 精靈會根據您的選擇設定來設定連接器，並建立連接。 如果您想要使用 PowerShell，我們也提供 PowerShell 腳本，您可以使用這些腳本來連接。

有關逐步指南，請參閱：

- [使用 Shifts 連接器精靈將 Shifts 連接到 Blue Yonder 員工管理](shifts-connector-wizard.md)
- [使用 PowerShell 將 Shifts 連接到 Blue Yonder 員工管理](shifts-connector-blue-yonder-powershell-setup.md)

設定連接之後，您隨時都可以使用 PowerShell 更新和變更連接設定。 至於連接器本身，您不必擔心升級或維護。 我們會處理好。

### <a name="reflexis-shifts-connector-for-microsoft-teams"></a>適用于 Microsoft Teams

適用于 Microsoft Teams 的 Reflexis Shifts 連接器是由斑馬系統託管和管理。 有了這個連接器，您可以將 Shifts 與 Reflexis WFM 系統整合，以管理您的排程，並保持其最新狀態。

前線員工可存取 Teams 中的班次排程，而且他們的要求會從 Shifts 同步處理至RWS (RWS) 。 在 RWS 中建立的要求和班次狀態會同步處理至 Teams。

:::image type="content" source="../../media/shifts-connector-reflexis.png" alt-text="螢幕擷取畫面顯示行動裝置上的班次清單，以及一份在 Reflexis 中的排程。" lightbox="../../media/shifts-connector-reflexis.png":::

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

每個連接器都隨附詳細的部署和組組指南。 它們包含 Azure Resource Manager (ARM) 部署腳本，讓您在 Microsoft Azure 中託管所有必要的Microsoft Azure。 原始程式碼和部署腳本可在 GitHub[中下載](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors)。 您可以根據需求進行部署或自訂或擴充。

若要深入瞭解，請參閱 [生產就緒的 Shifts 連接器](/microsoftteams/platform/samples/shifts-wfm-connectors)。

## <a name="related-articles"></a>相關文章

- [管理 Shifts 應用程式](manage-the-shifts-app-for-your-organization-in-teams.md)
