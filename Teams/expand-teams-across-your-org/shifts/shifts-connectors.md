---
title: Shifts 連接器
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解 Shifts 連接器，以及如何使用它們將 Shifts 連線到您的員工管理系統。
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: a4759bc010367e6531a557e2a5ff951d1b613505
ms.sourcegitcommit: 3b86e55787c34da76428d6915964ac4f3c6239fc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2022
ms.locfileid: "65598356"
---
# <a name="shifts-connectors"></a>Shifts 連接器

## <a name="overview"></a>概觀

Shifts 連接器可讓您將 Microsoft Teams 中的排程管理工具 Shifts 與您的員工管理 (WFM) 系統整合。 設定連線之後，第一線工作人員就可以從 Shifts 中順暢地在 WFM 系統中檢視和管理他們的排程。

將 WFM 系統連線至Teams可讓您的前線員工更有效率地管理排程，並簡化日常程式，提高參與度和生產力。 您的第一線工作人員有一個地方可以排程、通訊和共同作業，無論身在任何地方、在任何裝置上都需要完成工作。

本文提供 Shifts 連接器及其運作方式的概觀。

## <a name="how-shifts-connectors-work"></a>Shifts 連接器的運作方式

連接器會同步處理 WFM 系統和 Shifts 之間的排程資料，讓貴組織的排程Teams。 班次是您的第一線員工因其排程需求而參與的地方。 您的 WFM 系統是商務規則、合規性和智慧記錄的系統。

資料會透過連接器流向兩種方式，以確保排程永遠保持在最新狀態。 WFM 系統中的排程會同步處理至 [班次]。 此外，在 Shifts 中對排程所做的變更會即時同步回 WFM 系統。 做為記錄系統，在將資料儲存到 Shifts 之前，您的 WFM 系統會強制執行所有商務規則。

## <a name="managed-shifts-connectors"></a>受管理的 Shifts 連接器

受管理的 Shifts 連接器是與我們的合作夥伴共同開發的連接器。 受管理的連接器是由我們或我們的合作夥伴託管和管理。 使用受管理的連接器時，只需要最少的設定。

### <a name="microsoft-teams-shifts-connector-for-blue-yonder"></a>Microsoft Teams Blue Yonder 的 Shifts 連接器
<a name="blue_yonder"> </a>

Blue Yonder Teams Shifts 連接器是由 Microsoft 託管和管理的第一方產品。 使用此連接器，您可以將 Shifts 與 Blue Yonder 員工管理整合 (Blue Yonder WFM) 版本 2020.3、2021.1 或 2021.2，以管理您的排程並保持在最新狀態。  

> [!NOTE]
> 如果您有 Blue Yonder WFM 版本 2020.3 或 2021.1，請套用 2020.3.0.4 或 2021.1.0.3 修補程式。 此修補程式可修正使用者在 Shifts 中持續收到錯誤訊息的問題。 它也會修正導致使用者無法更新其在 Shifts 中的顯示狀態的問題。

:::image type="content" source="../../media/shifts-connector-blue-yonder.png" alt-text="螢幕擷取畫面顯示行動裝置上的 Shifts 調班要求、桌上型電腦上的 Teams 要求核准，以及 Blue Yonder WFM 中的排程。" lightbox="../../media/shifts-connector-blue-yonder.png":::

前線主管可以：

- 在 Blue Yonder WFM 中發佈班次和排程，然後在 Shifts 中檢視。
- 在 Blue Yonder WFM 中建立、管理及指派開放式班次，並在 Shifts 中檢視。
- 指派在 Shifts 中以 Blue Yonder WFM 建立的開啟班。
- 在 Blue Yonder WFM 中建立、編輯和刪除休假，並在 Shifts 中檢視。
- 在 Blue Yonder WFM 和 Shifts 中檢視及核准來自員工的排程要求。
- 在 Blue Yonder WFM 中設定和更新員工的顯示狀態，並在 Shifts 中檢視。

第一線工作人員可以：

- 在班次中查看他們自己和小組的班次和排程。
- 在班次中要求休假、開啟班次及調班。
- 在 Shifts 中設定它們的顯示狀態。

目前不支援下列動作：

- 在 Shifts 中新增、編輯、刪除、儲存或發佈班次。
- 在 Shifts 中新增、編輯、刪除、儲存或發佈休假。
- 在 Shifts 中新增、編輯、刪除、儲存或發佈開啟的班次。

當前線經理或工作人員嘗試在 Shifts 中執行任何這些動作時，他們會收到一則訊息，讓他們知道該動作不受支援。

#### <a name="example-scenario"></a>範例案例

主管 Eden 會在 Blue Yonder WFM 中發佈排程，該排程會透過連接器同步至 Teams 中的 Shifts。 員工成員 Alex 會在行動裝置上收到Teams通知，並檢視他的排程和指派的班次。

Alex 需要休息一段時間，並要求使用 Shifts 休息一天。 要求會透過連接器即時傳送至 Blue Yonder WFM。 Blue Yonder WFM 可確保要求符合商務規則，而且會建立要求。 Eden 會在 Blue Yonder WFM 中看到並核准要求，且核准會同步到Teams。  (Eden 也可以在 Shifts) 中查看及核准要求。 在Teams中，Alex 會收到他的要求已核准的通知，並檢視他的更新排程。

Alex 想要與同事調班。 在 Shifts 中，Alex 會在 Blue Yonder WFM 中看到根據商務規則，符合調班資格的所有班次清單。 Alex 選擇目前指派給 Gena 的班次。 Gena 會在行動裝置上Teams收到通知，並接受調班要求。 Eden 會在 Shifts 中看到並核准要求，而且核准會同步到 Blue Yonder WFM。  (Eden 也可以在 Blue Yonder WFM) 中查看及核准要求。 Alex 和 Gena 會在 Teams 中收到通知，並檢視他們更新的排程。

#### <a name="set-up-a-connection"></a>設定連線

使用連接器整合 Shifts 與 Blue Yonder WFM 只需要幾個步驟。 您可以使用Microsoft 365 系統管理中心中的 Shifts 連接器精靈來快速設定連線。 精靈會根據您選擇的設定設定來設定連接器，並建立連線。 如果您偏好使用 PowerShell，我們也會提供您可以用來連線的 PowerShell 腳本。

如需逐步指引，請參閱：

- [使用 Shifts 連接器精靈將 Shifts 連線到 Blue Yonder 員工管理](shifts-connector-wizard.md)
- [使用 PowerShell 將班次連線到 Blue Yonder 員工管理](shifts-connector-blue-yonder-powershell-setup.md)

設定連線之後，您可以隨時視需要使用 PowerShell 來更新和變更連線設定。 對於連接器本身，您不需要擔心升級或維護。 我們會處理。

### <a name="reflexis-shifts-connector-for-microsoft-teams"></a>Reflexis Shifts 連接器適用于 Microsoft Teams

Microsoft Teams的 Reflexis Shifts 連接器是由斑馬託管和管理。 使用此連接器，您可以將 Shifts 與 Reflexis WFM 系統整合，以管理您的排程並保持在最新狀態。

第一線員工可以存取他們在 Teams 中的班次排程，而且他們的要求會從班次同步處理至 Reflexis Workforce Scheduler (RWS) 。 在 RWS 中建立之要求和班次的狀態會同步處理至 Teams 中的 Shifts。

:::image type="content" source="../../media/shifts-connector-reflexis.png" alt-text="螢幕擷取畫面顯示行動裝置的班次清單和 Reflexis 中的排程。" lightbox="../../media/shifts-connector-reflexis.png":::

前線主管可以：

- 以 Reflexis 發佈班次和排程，並在 Shifts 中檢視。
- 編輯 Reflexis 和 Shifts 中的班次。
- 在 Reflexis 和 Shifts 中建立、管理和指派開放式班次。
- 檢視及核准來自 Reflexis 和 Shifts 中工作者的排程要求。

第一線工作人員可以：

- 在班次中查看他們自己和小組的班次和排程。
- 在 Shifts 中要求休假、開啟班次，以及調班和丟班。

若要深入瞭解，請移至 https://connect.zebra.com/microsoft-connectors 。

## <a name="related-articles"></a>相關文章

- [管理 Shifts 應用程式](manage-the-shifts-app-for-your-organization-in-teams.md)
