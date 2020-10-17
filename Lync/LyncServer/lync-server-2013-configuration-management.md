---
title: Lync Server 2013：設定管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration management
ms:assetid: 00ea1196-cb40-427f-99a4-5e8037cbf367
ms:mtpsurl: https://technet.microsoft.com/library/Dn720316(v=OCS.15)
ms:contentKeyID: 63969570
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de390f21c76a9636fc9ba2d6a7d3ee017681b6ba
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507830"
---
# <a name="configuration-management-in-lync-server-2013"></a>Lync Server 2013 中的設定管理

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-05-15_

設定管理是一種記錄和追蹤硬體和軟體資產及系統設定資訊的處理常式。 通常是用來追蹤軟體授權、維護用戶端電腦和伺服器的標準硬體和軟體組建，以及定義新電腦的命名標準。 設定管理通常涵蓋下列類別：

  - **硬體**    此類別會追蹤 IT 組織所擁有的設備元件、裝置所在位置，以及使用設備的人員。 這項資訊可讓組織規劃及預算升級、維護標準硬體組建、報告 IT 資產的價值以進行會計目的，以及協助防止盜竊。

  - **軟體**    此類別會追蹤安裝在每一部電腦上的軟體、版本號碼，以及授權的持有位置。 此資訊可協助您規劃升級，以確保軟體取得授權，並偵測是否存在未授權的 (和未經許可的) 軟體。

  - **標準組建**    此類別會為用戶端電腦和伺服器追蹤目前的標準組建，以及用戶端電腦和伺服器是否符合此標準。 定義及強制執行標準組建可協助支援人員，因為員工只需要維護一份軟體的有限數目的版本。

  - **累計更新和修復程式**    此類別會追蹤哪些 service pack 已測試並核准使用，以及哪些電腦是最新的。 這項資訊對於降低遭到損害的電腦風險及偵測已安裝未獲批准之更新的使用者來說很重要。

  - **系統組態資訊**    此類別會追蹤系統的功能、系統元素之間的互動，以及取決於執行順利之系統的處理常式。 例如，您可以在單一伺服器上設定協力廠商 proxy 伺服器。 應瞭解 proxy 伺服器對此伺服器的依賴性，如果失敗，可能需要應變計劃。 如果可將 proxy 伺服器設定為同時與其他前端伺服器通訊，則相依性和應急計畫可能會變更。

<div>

## <a name="implementing-configuration-management"></a>實施設定管理

決定需要管理的專案後，請透過收集資料和報告資料來執行設定管理。 小型組織最簡單的方法，就是以手動方式收集資料 (用戶端電腦的數目和模型，作業系統，已安裝軟體) ，並將其儲存在 Office Word 或 Office Excel 檔中。 針對較大型、更複雜且經常變更的系統，資產和詳細資訊集合的探索必須是自動化的。 決定組織的相關資訊，並將其記錄在資料庫中。

在下列方面，設定管理資料庫是支援人員和管理的有用工具：

  - **安全性審核**    資料庫可讓您識別執行 Lync Server 的伺服器，以及必須套用修補程式或已錯過安裝 service pack 或最新防病毒更新安裝之用戶端電腦系統的伺服器。

  - **軟體安裝**    識別用戶端軟體版本並加以追蹤，會協助系統管理員規劃版本更新及新的安裝，也會協助授權檔和符合性。

  - 設定**資訊**    如果您維護所有已變更其預設值之設定的最新清單，您將能夠快速且有效地疑難排解問題。

  - **規劃升級**    如果容量審查顯示您的 Lync 資料庫伺服器需要額外的儲存空間，請務必知道每個伺服器是否都有內部 RAID 控制器。 如果是的話，就是相同的模型？ 是否已安裝相同數目的磁片？ 設定管理資料庫會指出可以安裝的磁片類型、編號，以及每個案例中的升級路徑。

</div>

<div>

## <a name="tools-used-for-configuration-management"></a>設定管理所使用的工具

有許多工具可用於探索、審計及報告資產。 本節將討論其中的部分工具。

  - **自動化腳本**    您可以撰寫簡易腳本來報告諸如作業系統、service pack 層級等專案，以及特定電腦群組的軟體是否存在。 您可以將這些腳本撰寫為組織的確切需求。 不過，必要的腳本數目及其複雜性可能會使腳本的建立和維護成本高。

  - **自動化工具**    視您的業務規模和組織需求而定，您可能會想要考慮使用自動工具。 Microsoft 端點 Configuration Manager 等工具會結合標準報表範本 (例如 service pack 層級) ，也可讓您建立自訂報告（例如，針對自訂應用程式）。 Microsoft 端點 Configuration Manager 也可以用來報告硬體和軟體設定。

</div>

<div>

## <a name="relationship-with-change-management"></a>與變更管理的關聯

設定管理與變更管理密切相關。 設定管理可識別變更的需求，並識別及記錄發生變更的情況。 例如，設定管理資料庫可用於識別需要修復程式的伺服器。 變更管理會定義套用修復程式的程式。

相反地，如果新的累計更新已滾出，變更管理程式應將此資訊提供給設定管理系統。 設定管理工具可能需要加以設定，以識別新的軟體，讓他們能夠探索及追蹤軟體的部署位置和時間。

</div>

</div>

<span> </span>

</div>

</div>

</div>

