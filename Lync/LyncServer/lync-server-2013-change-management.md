---
title: Lync Server 2013： 變更管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Change management
ms:assetid: 73c774f5-c12f-4c72-be73-e07dc745b994
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720336(v=OCS.15)
ms:contentKeyID: 63969618
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: abd6af0af5722d05d7439ac262ff36e62d2b12e1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043955"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-management-in-lync-server-2013"></a>Lync Server 2013 中的變更管理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-08-18_

變更至 IT 環境會無法避免。 變更角色和責任，包括新的技術、 系統、 應用程式、 硬體、 工具、 程序，以及變更。 有效的變更管理系統，可讓您變更引入 IT 環境，快速且具有最少服務中斷。 變更管理系統整合在一起的團隊參與變更系統。 例如，若要利用 Office Web Apps 決定。 這是整合的 Lync 服務應用程式，可讓使用者讀取及編輯文件中的瀏覽器。 實作這項服務，您已經投入正式之後, 需要有幾個小組的參與程度：

  - **測試小組**   這小組負載測試 Office Web Apps 的測試伺服器上，提供預期的流量模式與預期的效能，實際執行伺服器的相關資訊的程序中。

  - **Lync 系統管理員**   此小組決定部署策略，並可能已安裝的指令碼。 小組負責確保變更部署在生產環境，並負責管理之後。 小組必須了解變更的效果，並將這些程序中所做的變更都放入實際執行環境之前

  - **網路團隊**   此小組負責變更允許從網際網路存取內部 Lync 集區伺服器的防火牆規則。 小組也負責中使用 Lync 系統管理員，確保可用頻寬可支援的額外負載。

  - **安全性小組**   此小組會評估安全性和風險降至最低。 安全性小組必須檢閱已知的弱點，並協助確保安全性風險會最小化。

  - **使用者接受度小組**   此小組組成願意測試系統並提供意見反應的改良功能的使用者。

變更管理程序定義的每個小組的責任，並排程工作，以執行，納入檢查與它們所需的測試。 變更控制項而定的複雜度和變更的預期的影響。 他們從自動核准的次要變更，若要變更為完整專案層級評論的檢閱會議，而異。 若要進一步說明這個，本節討論變更的群組。

  - **主要變更**   重大變更具有通用影響系統及可能需要從各種 microsoft teams 的輸入。 例如，這升級至 Lync Server 2013。 主要的變更會影響許多 microsoft teams 和或許是不同的系統。 變更管理程序可能會包含一或多個變更檢閱會議來通知的團隊都將會變更所涉及或變更所影響。

  - **重大變更**   重大變更，需要大量資源計劃、 建置及實作。 適當的變更控制項應採用以協助提升確定理解變更的影響、 測試部署程序，且 rollback 和緊急應變計劃已做好準備。 重大變更的範例部署新的累計更新。

  - **次要變更**   次要變更不會大幅影響 IT 環境中，例如，變更透過 Microsoft Lync Server 2013 控制台特定 Lync 原則。

  - **標準變更**   標準的變更會定期執行和容易理解且記錄。 變更管理程序應該檢閱程序的所有變更。 它應該不需要建立內容資料庫，或將使用者新增例行變更。

變更管理下列範例會檢查方式不同團隊互動，並部署新的 service pack 時，會執行的動作。 這些動作組織及管理的變更管理程序。

  - **引發變更要求**   安全性小組已評估最新的 service pack，並確認它在實際執行系統中可以解決可能弱點。 小組會引發變更要求給已套用到所有伺服器執行 Lync Server 的新累計更新。

  - **Service pack 發行 notes 檢閱**   Lync 管理員小組檢閱 service pack 版本資訊來識別系統上的效果。

  - **執行一系列的測試實驗室**   Lync 管理員小組必須決定是否 service pack 可以順利套用而不影響任何已安裝的應用程式與伺服器系統的測試環境中的伺服器上執行測試更新。 如果有協力廠商或內部建立介面的應用程式與 Lync Server，在實際執行環境中，這些應該也未經過測試。 這些測試也可以用來評估，才能執行升級的時間。

  - **使用者會通知的中斷**   Lync 管理員小組、 通訊小組或使用者支援工程師通知所有受影響的使用者的計劃的維護週期和多久服務將無法使用。

  - **Lync 的完整備份執行升級前**   Lync 管理員小組必須確認是有效的備份，可以用來安裝 service pack 失敗時還原成原來的系統狀態。 我們建議您備份，還原至待命伺服器至已備妥此系統，如果有問題。

  - **部署累計更新**   Lync 管理員小組並未計劃的維護週期期間安裝。

<div>

## <a name="managing-the-timing-of-changes"></a>管理變更的時機

我們建議您實作排程變更] 以避免干擾中重疊的工作的各節的程序。 例如，兩個小組可能同時規劃系統的次要變更。 一小組可能要套用累計更新或集區時另一個小組會將舊版使用者移轉至該集區。 未小組會受到其他小組規劃，變更和每個小組可能不一定是了解規劃其他小組的變更。 如果同時發生這兩種變更，可能會有問題實作所做的變更。 此外，如果之後所做的變更已套用有問題，例如，如果使用者移轉失敗，它可能難以決定哪些變更應該復原。 應該定期維護期間設定之間 IT 和測試所做的變更，並接受加以管理。

</div>

</div>

<span> </span>

</div>

</div>

</div>

