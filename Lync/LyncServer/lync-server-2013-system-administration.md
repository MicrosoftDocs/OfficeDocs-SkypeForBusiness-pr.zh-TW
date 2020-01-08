---
title: Lync Server 2013：系統管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: System administration
ms:assetid: 063eb962-b96a-4699-8579-bb7125112df4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720318(v=OCS.15)
ms:contentKeyID: 63969577
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d62526daf43308b4ed38538e5ea16e15b271fc9a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976460"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="system-administration-in-lync-server-2013"></a>Lync Server 2013 中的系統管理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-08-18_

系統管理包括日常管理工作（規劃中與隨選），這些任務必須讓 IT 系統保持順暢運作。 一般來說，系統管理工作是由書面程式所涵蓋。 這些程式可協助確保所有支援人員都使用相同的標準工具和方法。

在 Lync 環境中，典型的系統管理工作包括備份及封存池、監視記錄、建立及管理使用者，以及更新防毒軟體。

<div>

## <a name="system-troubleshooting"></a>系統疑難排解

組織必須準備好處理意外問題，而且應該有一個程式可以從報告的位置管理問題，直到其解析度。 關於如何診斷問題的相關資訊，應該在將來錄製並使用，以避免不必要的重複工作完成。

</div>

<div>

## <a name="system-troubleshooting-process"></a>系統疑難排解程式

下圖顯示系統疑難排解程式，以及與其他操作角色的互動。

**系統疑難排解流程圖**

![系統疑難排解]流程圖(images/Dn720318.869d0b89-6473-4b1f-9d90-59604b4b8e98(OCS.15).jpg "系統疑難排解流程圖")

  - **分類及優先順序**   ：此工作通常是由服務台所執行。 例如，問題可能會組成軟體問題或硬體問題。 接著該問題會傳送給適當的支援小組以進行調查。 判斷問題優先順序的規則，以及回應時間及解決時間，通常是在 SLA 中定義。

  - **調查與診斷**   適當的支援小組診斷問題，並建議變更以解決問題。 如果解決方案很簡單且不需要變更控制，就可以立即套用此方案。 如果方案不是很簡單，就應該引發變更要求，而建議的工作應該由變更管理程式來管理，通常是在「快速追蹤」程式底下。 所做的任何變更，都應該使用建構管理程式來記錄。

  - ****    測試解析度之後，請關閉並錄製問題，請關閉該問題。 如果有要從問題中學到的課程，請在知識庫中建立一個專案。

  - **審查及趨勢分析**   定期檢查最近的問題，以找出問題趨勢。 例如，如果使用者經常遇到無法登錄至 Lync 網站的問題，可能是網路頻寬問題造成的。 問題的解決時間，應對系統可用性造成任何停機的影響，都應該經過審查並與 SLA 進行比較。 Liaises 服務問題的人員（例如客戶管理員），應該會收到任何重要問題。

</div>

<div>

## <a name="issue-management-tools"></a>問題管理工具

服務台工具可讓員工記錄、分類，以及排定新問題的優先順序。 然後，工具會提供工作流程處理常式來透過調查與診斷來管理問題服務要求，通常是由一個以上的支援小組。 工具（通常會提供有關解析度時間與記錄趨勢的報告）也可能包含知識庫資料庫，可用於搜尋過去的問題。

Microsoft 知識庫是 Microsoft 所遇到之支援問題的實用記錄。 如需詳細資訊，請參閱 Microsoft 支援網站<http://go.microsoft.com/fwlink/?linkid=14898>（）。

協力廠商軟體通常需要自訂，以符合組織的需求，例如團隊的組織、報告需求，以及 SLA 所需的量值。

</div>

<div>

## <a name="centralized-vs-decentralized-administration"></a>集中化與分散式管理

執行系統管理工作的角色和職責，取決於組織是採用集中式模型、分散式模型，還是兩者的組合。

  - **集中式模型**   在集中式模型中，有一個或多個系統管理群組維持對整個 Lync Server 環境的完整控制。 此管理模型與資料中心類似，其中所有的管理工作都是由單一資訊技術群組來執行。 小組中的角色和職責應該根據經驗與專業知識來定義。

  - **分散模型**   分散組織位於多個地理位置，而且在不同的位置都能運作 Lync 伺服器伺服器和系統管理員團隊。 例如，您可能會有本機管理人員，以及一或多個針對每個國家/地區執行 Lync Server 2013 的伺服器。 或者，您可能會有一個伺服器池正在執行 Lync Server 2013，以及一個適用于北美的系統管理小組，一個用於歐洲。 有時候，您可能會希望系統管理員只負責自己的地理區域，並限制管理其他區域中資源的許可權。

Lync Server 也可讓您使用角色式存取控制（RBAC），將特定的管理工作委派給特定人員或群組。 RBAC 可讓管理員將特定的使用者權利和許可權委派給其他管理員，以執行可能的管理工作子集。 使用 RBAC，使用者執行特定系統管理工作的能力取決於指派給使用者的 RBAC 角色。 RBAC 會根據使用者所屬的 RBAC 角色，提供使用者可以執行的 Cmdlet 清單。

</div>

</div>

<span> </span>

</div>

</div>

</div>

