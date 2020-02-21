---
title: Lync Server 2013： 系統管理
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
ms.openlocfilehash: 87f128196f1d541e8a7f8ffd3b48bac8f34de85b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192236"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="system-administration-in-lync-server-2013"></a>Lync Server 2013 中的系統管理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-08-18_

系統管理包含的日常系統管理工作、 兩者計劃及依需求所需讓 IT 系統操作順暢。 一般而言，撰寫程序所涵蓋的系統管理工作。 這些程序可協助確保所有的支援人員，所使用的相同的標準工具和方法。

在 Lync 環境中，一般系統管理工作包括備份及封存集區、 監視記錄檔、 建立與管理使用者，以及更新防毒軟體。

<div>

## <a name="system-troubleshooting"></a>系統疑難排解

組織必須準備好處理未預期的問題，且應該具有從這些報告直到其解決方案在其中點管理問題的程序。 如何支援人員來診斷問題的相關資訊應記錄，且在未來用來避免不必要地重複已完成的工時。

</div>

<div>

## <a name="system-troubleshooting-process"></a>系統疑難排解程序

下圖顯示系統疑難排解程序和其他作業角色互動。

**系統疑難排解流程圖**

![系統疑難排解流程圖](images/Dn720318.869d0b89-6473-4b1f-9d90-59604b4b8e98(OCS.15).jpg "系統疑難排解流程圖")

  - **分類及排列優先順序**   通常由服務台執行這項工作。 例如，問題可能會分組為軟體問題或硬體問題。 問題是然後路由傳送到適當的支援小組的調查。 判斷問題，以及回應及解決問題，有時間的時間的優先順序的規則通常是在 SLA 中定義。

  - **調查並診斷**   適當支援小組診斷問題，並建議以解決問題的變更。 如果解決方案十分簡單，而且不需要變更控制，可立即套用解決方案。 如果解決方案並不容易，應該引發變更要求，並建議的工時應該由經常底下的 「 快速入門 」 程序的變更管理程序。 應該使用的組態管理程序記錄所做的任何變更。

  - **關閉並且將密碼記錄**   後測試解決方案時，應該關閉問題。 如果沒有此問題： 從學習課程，應該建立一個項目在知識庫中。

  - **檢閱及分析趨勢**   應該執行定期檢閱最近的問題，以識別問題的趨勢。 例如，如果使用者遇到緩慢的登入其 Lync 網站的常見問題，網路頻寬問題可能的原因。 應該檢閱，相較於 SLA 問題的解決時間，對於系統的可用性任何中斷的影響。 任何重大問題，應通知 liaises 與服務問題，例如帳戶管理員] 中，在客戶的人員。

</div>

<div>

## <a name="issue-management-tools"></a>此問題： 管理工具

Service desk 工具可讓人員來記錄、 分類，並排定優先順序新的問題。 接著工具會提供工作流程處理程序來管理此問題： 服務要求透過調查與診斷，通常由一個以上的支援小組。 工具，將會經常提供有關的解決時間與歷史趨勢報告，也可能包含知識庫資料庫中，可以用來搜尋整個過去的問題。

Microsoft 知識庫是很有用記錄遭遇到 microsoft 的支援問題。 如需詳細資訊，請參閱 Microsoft 支援網站 (<https://go.microsoft.com/fwlink/?linkid=14898>)。

協力廠商軟體通常需要自訂以符合組織的需求，例如 teams，報表需求，以及所需的 SLA 的量值的組織。

</div>

<div>

## <a name="centralized-vs-decentralized-administration"></a>集中式與管理對分散管理

角色與職責執行系統管理工作取決於組織遵循集中的模型、 分散式的模型中或兩者的組合。

  - **集中式模型**   在集中式模型中，一或多個系統管理群組會維護整個 Lync Server 環境的完整控制權。 此系統管理模型類似於由單一資訊技術群組執行所有的管理工作的資料中心。 您應該根據經驗及專業知識定義角色和責任小組內。

  - **分散模型**   分散式組織都位於多個地理位置且有可正常運作的 Lync Server 伺服器和小組的系統管理員的不同位置。 例如，有可能是本機系統管理人員和執行 Lync Server 2013 每個國家/地區的一個或多個伺服器。 或者，可能會有執行 Lync Server 2013 和北美地區的系統管理小組，一個用於歐洲的伺服器集區。 有時候，您可能想只負責自己的地理區域，並限制管理其他區域中的資源的權限的系統管理員。

Lync Server 也可讓您藉由使用角色型存取控制 (RBAC) 將特定的管理工作委派給特定人員或群組。 RBAC 允許委派特定的使用者權限和其他系統管理員執行的部分可能的管理工作的權限的系統管理員。 藉由使用 RBAC，使用者能夠執行特定的管理工作取決於指派給使用者的 RBAC 角色。 RBAC 會提供使用者又能執行的 cmdlet 根據使用者是成員的 RBAC 角色的清單。

</div>

</div>

<span> </span>

</div>

</div>

</div>

