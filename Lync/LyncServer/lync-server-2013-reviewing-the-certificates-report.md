---
title: Lync Server 2013：檢查憑證報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reviewing the Certificates Report
ms:assetid: 549cfc9b-3cc5-4483-a93c-fc0738c7f622
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558651(v=OCS.15)
ms:contentKeyID: 51541477
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a83167576746d3f90d96658b0dd3d65815f5375
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976445"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reviewing-the-certificates-report-in-lync-server-2013"></a>在 Lync Server 2013 中查看 [憑證] 報告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

[憑證] 報告包含建議的 Lync Server 2013 部署所需的所有憑證。 規劃工具帳戶會提供所輸入之主旨名稱和消費者的替代名稱。 未編輯的預設文字，可能會代表負責要求和頒發憑證的小組所面臨的潛在挑戰。 憑證資訊也會包含憑證的頒發位置資訊。 如果基礎結構沒有內部公開金鑰基礎結構（PKI），則可以透過公用證書提供者要求所有憑證。 [延伸金鑰用法（EKU）] 和 [指派給] 報表中的欄位，對於瞭解每個證書的用途和位置都很有説明。

![憑證管理員報告](images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "證書系統管理報告")

仔細檢查，並務必瞭解部署中每個憑證的使用及用途。 如果有關于憑證的問題，請判斷哪個伺服器或服務正在與其交談。 Lync Server 2013 中的憑證是用於兩個主要用途：

  - 相互傳輸層安全性（MTLS）：通訊中所涉及的電腦，每個都提供可向另一部電腦證明其身分識別的憑證。 這稱為伺服器驗證。 在每個電腦信任其他電腦的身分識別之後，才能開始進行通訊。

  - 加密-加密（安全通訊端層或 SSL，以及傳輸層安全性或 TLS）是協助保護通訊、協助確保隱私權，以及建立信任的通訊與共同作業系統的重要方式。

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中檢閱管理員報告](lync-server-2013-reviewing-the-administrator-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

