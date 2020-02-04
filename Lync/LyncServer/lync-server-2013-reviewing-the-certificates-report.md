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
ms.openlocfilehash: 410e9e99fccae7378b5260c9aa3a2281a3004cd5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733033"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reviewing-the-certificates-report-in-lync-server-2013"></a><span data-ttu-id="3cb02-102">在 Lync Server 2013 中查看 [憑證] 報告</span><span class="sxs-lookup"><span data-stu-id="3cb02-102">Reviewing the Certificates Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3cb02-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="3cb02-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="3cb02-104">[憑證] 報告包含建議的 Lync Server 2013 部署所需的所有憑證。</span><span class="sxs-lookup"><span data-stu-id="3cb02-104">The Certificates Report contains all certificates that are required in the recommended Lync Server 2013 deployment.</span></span> <span data-ttu-id="3cb02-105">規劃工具帳戶會提供所輸入之主旨名稱和消費者的替代名稱。</span><span class="sxs-lookup"><span data-stu-id="3cb02-105">The Planning Tool accounts for the subject names and subject alternative names that are entered.</span></span> <span data-ttu-id="3cb02-106">未編輯的預設文字，可能會代表負責要求和頒發憑證的小組所面臨的潛在挑戰。</span><span class="sxs-lookup"><span data-stu-id="3cb02-106">Default text that is left unedited may represent a potential challenge for the team responsible for requesting and issuing the certificates.</span></span> <span data-ttu-id="3cb02-107">憑證資訊也會包含憑證的頒發位置資訊。</span><span class="sxs-lookup"><span data-stu-id="3cb02-107">Certificate information also contains information about where the certificate can typically be issued from.</span></span> <span data-ttu-id="3cb02-108">如果基礎結構沒有內部公開金鑰基礎結構（PKI），則可以透過公用證書提供者要求所有憑證。</span><span class="sxs-lookup"><span data-stu-id="3cb02-108">If the infrastructure does not have an internal public key infrastructure (PKI) in place, all certificates can be requested through a public certificate provider.</span></span> <span data-ttu-id="3cb02-109">[延伸金鑰用法（EKU）] 和 [指派給] 報表中的欄位，對於瞭解每個證書的用途和位置都很有説明。</span><span class="sxs-lookup"><span data-stu-id="3cb02-109">Extended key usages (EKU) and Assign To fields in the report are very helpful in understanding what the purpose and location for each certificate should be.</span></span>

<span data-ttu-id="3cb02-110">![憑證管理員報告](images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "憑證管理員報告")</span><span class="sxs-lookup"><span data-stu-id="3cb02-110">![Certificates Admin Report](images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "Certificates Admin Report")</span></span>

<span data-ttu-id="3cb02-111">仔細檢查，並務必瞭解部署中每個憑證的使用及用途。</span><span class="sxs-lookup"><span data-stu-id="3cb02-111">Carefully review, and be sure to understand, the use and purpose of each certificate in the deployment.</span></span> <span data-ttu-id="3cb02-112">如果有關于憑證的問題，請判斷哪個伺服器或服務正在與其交談。</span><span class="sxs-lookup"><span data-stu-id="3cb02-112">If there is a question about what a certificate does, determine which server or service is talking to what.</span></span> <span data-ttu-id="3cb02-113">Lync Server 2013 中的憑證是用於兩個主要用途：</span><span class="sxs-lookup"><span data-stu-id="3cb02-113">Certificates in Lync Server 2013 are used for two primary purposes:</span></span>

  - <span data-ttu-id="3cb02-114">相互傳輸層安全性（MTLS）：通訊中所涉及的電腦，每個都提供可向另一部電腦證明其身分識別的憑證。</span><span class="sxs-lookup"><span data-stu-id="3cb02-114">Mutual Transport Layer Security (MTLS) – The computers involved in the communication each present a certificate that proves their identity to another computer.</span></span> <span data-ttu-id="3cb02-115">這稱為伺服器驗證。</span><span class="sxs-lookup"><span data-stu-id="3cb02-115">This is known as server authentication.</span></span> <span data-ttu-id="3cb02-116">在每個電腦信任其他電腦的身分識別之後，才能開始進行通訊。</span><span class="sxs-lookup"><span data-stu-id="3cb02-116">Communication cannot begin until each computer trusts the other computer’s identity.</span></span>

  - <span data-ttu-id="3cb02-117">加密-加密（安全通訊端層或 SSL，以及傳輸層安全性或 TLS）是協助保護通訊、協助確保隱私權，以及建立信任的通訊與共同作業系統的重要方式。</span><span class="sxs-lookup"><span data-stu-id="3cb02-117">Encryption – Encryption (Secure Sockets Layer, or SSL, and Transport Layer Security, or TLS) is a critical means to help secure communications, help ensure privacy, and to create a trusted communications and collaboration system.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="3cb02-118">請參閱</span><span class="sxs-lookup"><span data-stu-id="3cb02-118">See Also</span></span>


[<span data-ttu-id="3cb02-119">在 Lync Server 2013 中檢閱管理員報告</span><span class="sxs-lookup"><span data-stu-id="3cb02-119">Reviewing the Administrator Reports in Lync Server 2013</span></span>](lync-server-2013-reviewing-the-administrator-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

