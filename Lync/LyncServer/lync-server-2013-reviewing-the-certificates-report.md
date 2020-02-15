---
title: Lync Server 2013： 檢閱憑證報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reviewing the Certificates Report
ms:assetid: 549cfc9b-3cc5-4483-a93c-fc0738c7f622
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558651(v=OCS.15)
ms:contentKeyID: 51541477
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26a01f778e855fc5934b524c5bf4a5829a2ca31e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051557"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reviewing-the-certificates-report-in-lync-server-2013"></a>檢閱憑證報告在 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-21_

憑證報告包含建議的 Lync Server 2013 部署中所需的所有憑證。 主體名稱和主體替代名稱所輸入的規劃工具帳戶。 預設會保持未編輯的文字可能代表負責要求和發出憑證的小組潛在挑戰。 憑證資訊同時包含憑證一般發行來源的相關資訊。 如果基礎結構不存在內部公開金鑰基礎結構 (PKI)，則所有憑證皆可透過公開憑證提供者要求。 報告中的「擴充金鑰使用方法 (EKU)」與「指派給」欄位對於了解每一個憑證的用途及歸屬位置非常有用。

![憑證管理員報告](images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "憑證管理員報告")

仔細檢閱，並請務必了解，使用並部署中的每個憑證的用途。 如果有疑問憑證用途，判斷哪一個伺服器或服務會與交談項目。 Lync Server 2013 中的憑證用於兩個主要的用途：

  - 相互傳輸層安全性 (MTLS) – 在每個通訊中，在相關的電腦呈現另一部電腦證明其身分識別的憑證。 這稱為伺服器驗證。 通訊無法開始，直到每一部電腦信任另一部電腦的身分識別。

  - 加密 – 加密 (安全通訊端層，或稱為 SSL，以及傳輸層安全性，或稱為 TLS) 是協助保障通訊安全、確保隱私，以及建立信任的通訊與共同作業系統的重要方法。

<div>

## <a name="see-also"></a>另請參閱


[檢閱 Lync Server 2013 中的系統管理員報告](lync-server-2013-reviewing-the-administrator-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

