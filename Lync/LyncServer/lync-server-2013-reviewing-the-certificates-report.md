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
ms.openlocfilehash: 9c751de439ef84e718ed1d21e43c11be89cc28fe
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201279"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="reviewing-the-certificates-report-in-lync-server-2013"></a><span data-ttu-id="e27bf-102">檢閱憑證報告在 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e27bf-102">Reviewing the Certificates Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e27bf-103">_**上次修改主題：** 2013年-02-21_</span><span class="sxs-lookup"><span data-stu-id="e27bf-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="e27bf-104">憑證報告包含建議的 Lync Server 2013 部署中所需的所有憑證。</span><span class="sxs-lookup"><span data-stu-id="e27bf-104">The Certificates Report contains all certificates that are required in the recommended Lync Server 2013 deployment.</span></span> <span data-ttu-id="e27bf-105">主體名稱和主體替代名稱所輸入的規劃工具帳戶。</span><span class="sxs-lookup"><span data-stu-id="e27bf-105">The Planning Tool accounts for the subject names and subject alternative names that are entered.</span></span> <span data-ttu-id="e27bf-106">預設會保持未編輯的文字可能代表負責要求和發出憑證的小組潛在挑戰。</span><span class="sxs-lookup"><span data-stu-id="e27bf-106">Default text that is left unedited may represent a potential challenge for the team responsible for requesting and issuing the certificates.</span></span> <span data-ttu-id="e27bf-107">憑證資訊同時包含憑證一般發行來源的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="e27bf-107">Certificate information also contains information about where the certificate can typically be issued from.</span></span> <span data-ttu-id="e27bf-108">如果基礎結構不存在內部公開金鑰基礎結構 (PKI)，則所有憑證皆可透過公開憑證提供者要求。</span><span class="sxs-lookup"><span data-stu-id="e27bf-108">If the infrastructure does not have an internal public key infrastructure (PKI) in place, all certificates can be requested through a public certificate provider.</span></span> <span data-ttu-id="e27bf-109">報告中的「擴充金鑰使用方法 (EKU)」與「指派給」欄位對於了解每一個憑證的用途及歸屬位置非常有用。</span><span class="sxs-lookup"><span data-stu-id="e27bf-109">Extended key usages (EKU) and Assign To fields in the report are very helpful in understanding what the purpose and location for each certificate should be.</span></span>

<span data-ttu-id="e27bf-110">![憑證管理員報告](images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "憑證管理員報告")</span><span class="sxs-lookup"><span data-stu-id="e27bf-110">![Certificates Admin Report](images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "Certificates Admin Report")</span></span>

<span data-ttu-id="e27bf-111">仔細檢閱，並請務必了解，使用並部署中的每個憑證的用途。</span><span class="sxs-lookup"><span data-stu-id="e27bf-111">Carefully review, and be sure to understand, the use and purpose of each certificate in the deployment.</span></span> <span data-ttu-id="e27bf-112">如果有疑問憑證用途，判斷哪一個伺服器或服務會與交談項目。</span><span class="sxs-lookup"><span data-stu-id="e27bf-112">If there is a question about what a certificate does, determine which server or service is talking to what.</span></span> <span data-ttu-id="e27bf-113">Lync Server 2013 中的憑證用於兩個主要的用途：</span><span class="sxs-lookup"><span data-stu-id="e27bf-113">Certificates in Lync Server 2013 are used for two primary purposes:</span></span>

  - <span data-ttu-id="e27bf-114">相互傳輸層安全性 (MTLS) – 在每個通訊中，在相關的電腦呈現另一部電腦證明其身分識別的憑證。</span><span class="sxs-lookup"><span data-stu-id="e27bf-114">Mutual Transport Layer Security (MTLS) – The computers involved in the communication each present a certificate that proves their identity to another computer.</span></span> <span data-ttu-id="e27bf-115">這稱為伺服器驗證。</span><span class="sxs-lookup"><span data-stu-id="e27bf-115">This is known as server authentication.</span></span> <span data-ttu-id="e27bf-116">通訊無法開始，直到每一部電腦信任另一部電腦的身分識別。</span><span class="sxs-lookup"><span data-stu-id="e27bf-116">Communication cannot begin until each computer trusts the other computer’s identity.</span></span>

  - <span data-ttu-id="e27bf-117">加密 – 加密 (安全通訊端層，或稱為 SSL，以及傳輸層安全性，或稱為 TLS) 是協助保障通訊安全、確保隱私，以及建立信任的通訊與共同作業系統的重要方法。</span><span class="sxs-lookup"><span data-stu-id="e27bf-117">Encryption – Encryption (Secure Sockets Layer, or SSL, and Transport Layer Security, or TLS) is a critical means to help secure communications, help ensure privacy, and to create a trusted communications and collaboration system.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="e27bf-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e27bf-118">See Also</span></span>


[<span data-ttu-id="e27bf-119">檢閱 Lync Server 2013 中的系統管理員報告</span><span class="sxs-lookup"><span data-stu-id="e27bf-119">Reviewing the Administrator Reports in Lync Server 2013</span></span>](lync-server-2013-reviewing-the-administrator-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

