---
title: Lync Server 2013：系統管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: System administration
ms:assetid: 063eb962-b96a-4699-8579-bb7125112df4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720318(v=OCS.15)
ms:contentKeyID: 63969577
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c830b689f0f55c2af191443583394e9f8c22eed
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48497500"
---
# <a name="system-administration-in-lync-server-2013"></a>Lync Server 2013 中的系統管理

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-08-18_

系統管理包括一天的日常管理工作，也就是已計畫及隨需的管理工作，都是讓 IT 系統保持順利運作所需的作業。 通常，系統管理工作會在書面程式中涵蓋。 這些程式可協助確保所有支援人員都使用相同的標準工具和方法。

在 Lync 環境中，一般系統管理工作包括備份及封存集區、監控記錄檔、建立及管理使用者，以及更新防毒軟體。

<div>

## <a name="system-troubleshooting"></a>系統疑難排解

組織必須準備好處理未預期的問題，而且應該有一個程式可從報告問題的位置開始，直到解決問題為止。 有關如何診斷問題之支援人員的資訊應該記錄下來，以備今後使用，以避免不必要的重複作業。

</div>

<div>

## <a name="system-troubleshooting-process"></a>系統疑難排解程式

下圖顯示系統疑難排解程式以及與其他作業角色的互動。

**系統疑難排解流程圖**

![系統疑難排解流程圖](images/Dn720318.869d0b89-6473-4b1f-9d90-59604b4b8e98(OCS.15).jpg "系統疑難排解流程圖")

  - **分類及優先順序**    此工作通常是由服務台執行。 例如，問題可能會歸群組為軟體問題或硬體問題。 然後將問題路由傳送給適當的支援小組進行調查。 判斷問題優先順序的規則以及回應的時間及解決時間，通常是在 SLA 中定義的。

  - **調查和診斷**    適當的支援小組會診斷問題，並建議變更以解決問題。 如果解決方案很簡單且不需要變更控制，則可以立即套用解決方案。 如果解決方案不是很簡單，應會引發變更要求，而建議的工作應該由變更管理程式（通常是「快速追蹤」）來管理。 所做的任何變更都應該使用設定管理程式來記錄。

  - **Close 和 Record**    測試解決方法後，應關閉問題。 如果有從問題中學到的課程，應在知識庫中建立專案。

  - **回顧和趨勢分析**    應該定期複查最近的問題，以找出問題趨勢。 例如，如果使用者發生經常的登入至其 Lync 網站的問題，可能是網路頻寬問題。 問題的解決時間，應檢查任何中斷系統可用性的影響，並與 SLA 進行比較。 與客戶 liaises 服務問題（如帳戶管理員）的人員應該知道任何重大問題。

</div>

<div>

## <a name="issue-management-tools"></a>問題管理工具

服務台工具可讓員工記錄、分類及優先順序新的問題。 然後，工具會提供工作流程處理常式，透過調查和診斷來管理問題服務要求，這通常是由多個支援小組進行。 工具（通常會提供有關解析度時間及歷史趨勢的報告）可能也會包含知識庫資料庫，可用於搜尋過去的問題。

Microsoft 知識庫是 Microsoft 所遇到支援問題的有用記錄。 如需詳細資訊，請參閱 Microsoft 支援網站 (<https://go.microsoft.com/fwlink/?linkid=14898>) 。

協力廠商軟體通常需要自訂，以符合組織的需求，例如小組組織、報告需求，以及 SLA 所需的量值。

</div>

<div>

## <a name="centralized-vs-decentralized-administration"></a>集中式管理與分散式管理

執行系統管理工作的角色和責任取決於組織遵循集中式模型、分散式模型或兩者的組合。

  - **集中式模型**    在集中式模型中，一或多個系統管理群組維護完整的 Lync 伺服器環境控制。 這種系統管理模型類似于資料中心，所有的管理工作都是由單一資訊技術群組執行。 小組中的角色和責任應根據經驗和專業知識加以定義。

  - **分散模型**    分散組織位於數個地理位置，且在不同的位置運作 Lync Server 伺服器和管理員團隊。 例如，對於每個國家/地區，可能會有本機管理人員和一或多部執行 Lync Server 2013 的伺服器。 或者，您可能會有執行 Lync Server 2013 的伺服器集區，以及一部適用于北美和第一版的系統管理團隊。 在某些情況下，您可能會想要讓系統管理員只負責其專屬地理區域，並限制管理其他區域中資源的許可權。

Lync Server 也可讓您使用以角色為基礎的存取控制 (RBAC) ，將特定的管理工作委派給特定人員或群組。 RBAC 可讓系統管理員將特定使用者權利和許可權委派給其他管理員，以執行可能的系統管理工作子集。 透過使用 RBAC，使用者執行特定系統管理工作的能力，會根據指派給使用者的 RBAC 角色而定。 RBAC 提供使用者可根據使用者隸屬之 RBAC 角色執行的 Cmdlet 清單。

</div>

</div>

<span> </span>

</div>

</div>

</div>

