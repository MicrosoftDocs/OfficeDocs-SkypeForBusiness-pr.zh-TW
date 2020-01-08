---
title: Lync Server 2013：建構管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuration management
ms:assetid: 00ea1196-cb40-427f-99a4-5e8037cbf367
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720316(v=OCS.15)
ms:contentKeyID: 63969570
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa4bacdea1090351e9937e039fec184a1f59ab0f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975541"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuration-management-in-lync-server-2013"></a>Lync Server 2013 中的建構管理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-05-15_

[設定管理] 是記錄及追蹤硬體和軟體資產及系統設定資訊的程式。 它通常用來追蹤軟體授權、維護用戶端電腦和伺服器的標準硬體和軟體組建，以及定義新電腦的命名標準。 建構管理通常涵蓋下列類別：

  - **硬體**   ：此類別會追蹤 IT 組織擁有的裝置、裝置所在的位置，以及使用裝置的人員。 這項資訊可讓組織規劃和預算以進行升級、維護標準硬體組建、針對會計用途報告 IT 資產價值，並協助防範盜竊。

  - **軟體**   這個類別會追蹤安裝在每個電腦上的軟體、版本號碼，以及這些授權的保留位置。 此資訊可協助您規劃升級、確保軟體擁有授權，並偵測是否有未授權（與未經許可）的軟體。

  - **標準組建**   這個類別會追蹤用戶端電腦和伺服器的目前標準組建，以及用戶端電腦和伺服器是否符合此標準。 定義並強制執行標準組建可協助支援人員，因為員工必須只維持有限數量的每個軟體版本。

  - **累積更新與修正程式**   此類別會追蹤哪些 service pack 已測試並經過核准，且哪些電腦是最新的。 這項資訊對於降低電腦遭到破壞的風險，以及偵測已安裝未獲核准更新的使用者來說，是非常重要的。

  - **系統設定資訊**   ：這個類別會追蹤系統的功能、系統元素之間的互動，以及依賴于正常執行的系統的進程。 例如，協力廠商 proxy 伺服器可以在單一伺服器上設定。 必須瞭解 proxy 伺服器對此伺服器的依賴性，而且如果發生失敗，可能也會需要應急方案。 如果 proxy 伺服器也可以設定為與其他前端伺服器通訊，相依性與應急方案可能會變更。

<div>

## <a name="implementing-configuration-management"></a>實施設定管理

在您決定需要管理哪些專案之後，請收集資料並報告資料來執行設定管理。 小型組織最簡單的方法就是手動收集資料（用戶端電腦、作業系統、已安裝軟體的數量及模型），並將它儲存在 Office Word 或 Office Excel 檔中。 對於較大、較複雜且不斷變更的系統，資產和詳細資訊的探索必須是自動化的。 決定與貴組織相關的資訊，並將其記錄在資料庫中。

在下欄區域中，配置管理資料庫是支援人員和管理的公用程式：

  - **安全性審核**   ：資料庫可讓您找出執行 Lync Server 及用戶端電腦系統的伺服器，這些伺服器必須已套用熱修復程式，或已錯過安裝 service pack 或最新的防病毒更新。

  - **軟體安裝**   ：識別用戶端軟體版本並追蹤它們將協助系統管理員規劃版本更新與新的安裝，也可協助取得授權檔與合規性。

  - **配置資訊**   ：如果您維護的是所有設定的最新清單，且其預設值已變更，就能快速且更有效率地進行問題的疑難排解。

  - **規劃升級**   如果容量審查發現您的 Lync 資料庫伺服器上需要額外的儲存空間，請務必知道每個伺服器是否都有內部 RAID 控制器。 如果有的話，那就是相同的模型嗎？ 是否已安裝相同數量的磁片？ [設定管理] 資料庫會指出可以安裝的磁片類型、編號，以及每個案例中的升級路徑。

</div>

<div>

## <a name="tools-used-for-configuration-management"></a>建構管理所用的工具

您可以透過多種工具來探索、審核及報告資產。 本節將討論其中一些工具。

  - **自動腳本**   您可以撰寫簡單的腳本來報告諸如作業系統、service pack 層級等專案，以及軟體是否存在於特定電腦群組上。 您可以將這些腳本撰寫成組織的確切需求。 不過，所需的腳本數及其複雜性可能會使腳本的建立和維護成本高昂。

  - **自動化工具**   根據您的企業規模與組織的需求而定，您可能會想要考慮使用自動工具。 系統中心 Configuration Manager 等工具會結合標準報表範本（例如 service pack 層級），也可讓您建立自訂的報表（例如，自訂的應用程式）。 系統中心 Configuration Manager 也可以用來報告硬體和軟體設定。

</div>

<div>

## <a name="relationship-with-change-management"></a>與變更管理的關聯

建構管理與變更管理密切相關。 [建構管理] 可識別變更的需求，並確認和記錄發生變更的情況。 例如，您可以使用配置管理資料庫來識別需要修復程式的伺服器。 變更管理然後定義應用程式的應用程式。

相反地，如果新的累加更新是推出，則變更管理程式應該會將此資訊提供給建構管理系統。 建構管理工具可能需要進行設定，以識別新的軟體，讓他們能夠探索並追蹤軟體部署的位置和時間。

</div>

</div>

<span> </span>

</div>

</div>

</div>

