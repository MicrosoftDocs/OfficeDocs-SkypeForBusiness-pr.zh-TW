---
title: Lync Server 2013：檢查憑證報告
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
ms.openlocfilehash: 78460666e588ca60249e0c9d8aed8b5870256445
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511340"
---
# <a name="reviewing-the-certificates-report-in-lync-server-2013"></a>在 Lync Server 2013 中檢查憑證報告

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

憑證報告包含建議的 Lync Server 2013 部署中所需的所有憑證。 規劃工具會為所輸入的主旨名稱和主體替代名稱提供帳戶。 未編輯的預設文字可能代表負責要求及簽發憑證的小組潛在挑戰。 憑證資訊同時包含憑證一般發行來源的相關資訊。 如果基礎結構不存在內部公開金鑰基礎結構 (PKI)，則所有憑證皆可透過公開憑證提供者要求。 報告中的「擴充金鑰使用方法 (EKU)」與「指派給」欄位對於了解每一個憑證的用途及歸屬位置非常有用。

![憑證管理員報告](images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "憑證管理員報告")

請認真檢查，並務必瞭解部署中每個憑證的使用和用途。 如果有關于憑證用途的問題，請判斷哪個伺服器或服務與哪個服務交談。 Lync Server 2013 中的憑證是用於兩個主要目的：

  - 相互傳輸層安全性 (MTLS) –通訊中所涉及的各台電腦都會呈現憑證，證明其身分識別至其他電腦。 這稱為「伺服器驗證」。 在每一部電腦信任另一部電腦的身分識別之前，無法開始通訊。

  - 加密 – 加密 (安全通訊端層，或稱為 SSL，以及傳輸層安全性，或稱為 TLS) 是協助保障通訊安全、確保隱私，以及建立信任的通訊與共同作業系統的重要方法。

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中審閱管理員報告](lync-server-2013-reviewing-the-administrator-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

