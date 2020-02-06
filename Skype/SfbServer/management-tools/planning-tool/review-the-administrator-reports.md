---
title: 在商務用 Skype Server 2015 中查看系統管理員報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 22d480ea-cd64-4d09-99fe-96e997570844
description: 系統管理員報告是部署與作業的詳細資訊。 報告是根據設計網站中標示的選取產生的。 設計工具可以編輯網狀圖並定義伺服器、池及負載平衡器的完整 IP 位址及完整功能變數名稱（Fqdn），進一步為系統管理員報告增添價值。
ms.openlocfilehash: ae6dba3f5967fcd10618a8ab53c754a4f38da748
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816292"
---
# <a name="review-the-administrator-reports-in-skype-for-business-server-2015"></a><span data-ttu-id="c6f90-105">在商務用 Skype Server 2015 中查看系統管理員報告</span><span class="sxs-lookup"><span data-stu-id="c6f90-105">Review the Administrator Reports in Skype for Business Server 2015</span></span>

<span data-ttu-id="c6f90-106">系統管理員報告是部署與作業的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="c6f90-106">The Administrator Reports are detailed information for deployment and operations.</span></span> <span data-ttu-id="c6f90-107">報告是根據**設計網站**中標示的選取產生的。</span><span class="sxs-lookup"><span data-stu-id="c6f90-107">The reports are generated based on the selections marked in **Design Sites**.</span></span> <span data-ttu-id="c6f90-108">設計工具可以編輯網狀圖並定義伺服器、池及負載平衡器的完整 IP 位址及完整功能變數名稱（Fqdn），進一步為系統管理員報告增添價值。</span><span class="sxs-lookup"><span data-stu-id="c6f90-108">The designer can further add value to the Administrator Reports by editing the network diagrams and defining the complete IP addresses and fully qualified domain names (FQDNs) for servers, pools, and load balancers.</span></span>

<span data-ttu-id="c6f90-109">[管理員報告] 功能可讓您：</span><span class="sxs-lookup"><span data-stu-id="c6f90-109">The Administrator reports feature allows you to:</span></span>

- [<span data-ttu-id="c6f90-110">審閱摘要報告</span><span class="sxs-lookup"><span data-stu-id="c6f90-110">Review the Summary Report</span></span>](review-the-administrator-reports.md#Summary_report)

- [<span data-ttu-id="c6f90-111">查看憑證報告</span><span class="sxs-lookup"><span data-stu-id="c6f90-111">Review the Certificates Report</span></span>](review-the-administrator-reports.md#Certificates_Report)

- [<span data-ttu-id="c6f90-112">查看防火牆報告</span><span class="sxs-lookup"><span data-stu-id="c6f90-112">Review the Firewall Report</span></span>](review-the-administrator-reports.md#Firewall_report)

- [<span data-ttu-id="c6f90-113">查看 DNS 報告</span><span class="sxs-lookup"><span data-stu-id="c6f90-113">Review the DNS Report</span></span>](review-the-administrator-reports.md#DNS_Report)

## <a name="review-the-summary-report"></a><span data-ttu-id="c6f90-114">審閱摘要報告</span><span class="sxs-lookup"><span data-stu-id="c6f90-114">Review the Summary Report</span></span>
<span data-ttu-id="c6f90-115"><a name="Summary_report"> </a></span><span class="sxs-lookup"><span data-stu-id="c6f90-115"><a name="Summary_report"> </a></span></span>

<span data-ttu-id="c6f90-116">商務用 Skype 系統管理員報告是四個重要報表中的第一筆，以詳細說明您的設計。</span><span class="sxs-lookup"><span data-stu-id="c6f90-116">The Skype for Business Administrator Report is the first of four valuable reports that document your design in detail.</span></span> <span data-ttu-id="c6f90-117">此報告中的資訊，以及其他三個相關聯的報表，對於您的資訊技術團隊很有用：</span><span class="sxs-lookup"><span data-stu-id="c6f90-117">The information in this report, and the other three associated reports, is useful for your Information Technology Teams:</span></span>

![一般摘要管理員報告](../../media/General_Summary_Report_Admin_Report.png)

<span data-ttu-id="c6f90-119">[摘要報告] 會列出與 Edge 網路相關的一般配置資訊。</span><span class="sxs-lookup"><span data-stu-id="c6f90-119">The Summary Report lists general configuration information associated with your Edge network.</span></span> <span data-ttu-id="c6f90-120">[位置]、[完全合格的功能變數名稱（FQDN）] 和 [IP 位址]、[網路類型]，以及特定于指定角色的批註，都有記錄。</span><span class="sxs-lookup"><span data-stu-id="c6f90-120">The location, fully qualified domain name (FQDN) and IP address, type of network, and comments specific to a given role are documented.</span></span>

<span data-ttu-id="c6f90-121">設計人員以及要部署、管理及維護基礎結構的每個小組，都應該檢查摘要報告的準確性，並確認錯誤最低。</span><span class="sxs-lookup"><span data-stu-id="c6f90-121">The designer and each of the teams that will deploy, manage, and maintain the infrastructure should review the summary report for accuracy and to make sure that errors are at a minimum.</span></span>

<span data-ttu-id="c6f90-122">您也可以查看更詳細的報表：</span><span class="sxs-lookup"><span data-stu-id="c6f90-122">You can also view more detailed reports:</span></span>

- <span data-ttu-id="c6f90-123">憑證報告</span><span class="sxs-lookup"><span data-stu-id="c6f90-123">Certificates Report</span></span>

- <span data-ttu-id="c6f90-124">防火牆報告</span><span class="sxs-lookup"><span data-stu-id="c6f90-124">Firewall Report</span></span>

- <span data-ttu-id="c6f90-125">DNS 報告</span><span class="sxs-lookup"><span data-stu-id="c6f90-125">DNS Report</span></span>

## <a name="review-the-certificates-report"></a><span data-ttu-id="c6f90-126">查看憑證報告</span><span class="sxs-lookup"><span data-stu-id="c6f90-126">Review the Certificates Report</span></span>
<span data-ttu-id="c6f90-127"><a name="Certificates_Report"> </a></span><span class="sxs-lookup"><span data-stu-id="c6f90-127"><a name="Certificates_Report"> </a></span></span>

<span data-ttu-id="c6f90-128">[憑證] 報告包含建議的商務用 Skype Server 2015 部署所需的所有憑證。</span><span class="sxs-lookup"><span data-stu-id="c6f90-128">The Certificates Report contains all certificates that are required in the recommended Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="c6f90-129">規劃工具帳戶會提供所輸入之主旨名稱和消費者的替代名稱。</span><span class="sxs-lookup"><span data-stu-id="c6f90-129">The Planning Tool accounts for the subject names and subject alternative names that are entered.</span></span> <span data-ttu-id="c6f90-130">未編輯的預設文字，可能會代表負責要求和頒發憑證的小組所面臨的潛在挑戰。</span><span class="sxs-lookup"><span data-stu-id="c6f90-130">Default text that is left unedited may represent a potential challenge for the team responsible for requesting and issuing the certificates.</span></span> <span data-ttu-id="c6f90-131">憑證資訊也會包含憑證的頒發位置資訊。</span><span class="sxs-lookup"><span data-stu-id="c6f90-131">Certificate information also contains information about where the certificate can typically be issued from.</span></span> <span data-ttu-id="c6f90-132">如果基礎結構沒有內部公開金鑰基礎結構（PKI），則可以透過公用證書提供者要求所有憑證。</span><span class="sxs-lookup"><span data-stu-id="c6f90-132">If the infrastructure does not have an internal public key infrastructure (PKI) in place, all certificates can be requested through a public certificate provider.</span></span> <span data-ttu-id="c6f90-133">[延伸金鑰用法（EKU）] 和 [指派給] 報表中的欄位，對於瞭解每個證書的用途和位置都很有説明。</span><span class="sxs-lookup"><span data-stu-id="c6f90-133">Extended key usages (EKU) and Assign To fields in the report are very helpful in understanding what the purpose and location for each certificate should be.</span></span>

![憑證管理員報告](../../media/Certificates_Report_Admin_Report.png)

<span data-ttu-id="c6f90-135">仔細檢查，並務必瞭解部署中每個憑證的使用及用途。</span><span class="sxs-lookup"><span data-stu-id="c6f90-135">Carefully review, and be sure to understand, the use and purpose of each certificate in the deployment.</span></span> <span data-ttu-id="c6f90-136">如果有關于憑證的問題，請判斷哪個伺服器或服務正在與其交談。</span><span class="sxs-lookup"><span data-stu-id="c6f90-136">If there is a question about what a certificate does, determine which server or service is talking to what.</span></span> <span data-ttu-id="c6f90-137">商務用 Skype Server 2015 中的憑證是用於兩個主要用途：</span><span class="sxs-lookup"><span data-stu-id="c6f90-137">Certificates in Skype for Business Server 2015 are used for two primary purposes:</span></span>

- <span data-ttu-id="c6f90-138">相互傳輸層安全性（MTLS）：通訊中所涉及的電腦，每個都提供可向其他電腦證明其身分身分的憑證。</span><span class="sxs-lookup"><span data-stu-id="c6f90-138">Mutual Transport Layer Security (MTLS) - The computers involved in the communication each present a certificate that proves their identity to another computer.</span></span> <span data-ttu-id="c6f90-139">這稱為伺服器驗證。</span><span class="sxs-lookup"><span data-stu-id="c6f90-139">This is known as server authentication.</span></span> <span data-ttu-id="c6f90-140">在每個電腦信任其他電腦的身分識別之後，才能開始進行通訊。</span><span class="sxs-lookup"><span data-stu-id="c6f90-140">Communication cannot begin until each computer trusts the other computer's identity.</span></span>

- <span data-ttu-id="c6f90-141">加密-加密（安全通訊端層或 SSL，以及傳輸層安全性或 TLS）是協助保護通訊、協助確保隱私權，以及建立信任的通訊與共同作業系統的重要方式。</span><span class="sxs-lookup"><span data-stu-id="c6f90-141">Encryption - Encryption (Secure Sockets Layer, or SSL, and Transport Layer Security, or TLS) is a critical means to help secure communications, help ensure privacy, and to create a trusted communications and collaboration system.</span></span>

## <a name="review-the-firewall-report"></a><span data-ttu-id="c6f90-142">查看防火牆報告</span><span class="sxs-lookup"><span data-stu-id="c6f90-142">Review the Firewall Report</span></span>
<span data-ttu-id="c6f90-143"><a name="Firewall_report"> </a></span><span class="sxs-lookup"><span data-stu-id="c6f90-143"><a name="Firewall_report"> </a></span></span>

<span data-ttu-id="c6f90-144">商務用 Skype Server 2015 有一組可能複雜的防火牆規則。</span><span class="sxs-lookup"><span data-stu-id="c6f90-144">Skype for Business Server 2015 has a potentially complex set of firewall rules.</span></span> <span data-ttu-id="c6f90-145">規劃工具會根據設計人員的輸入準則，透過產生一個定義來詳細說明所有防火牆需求的報告，來減少這項複雜性。</span><span class="sxs-lookup"><span data-stu-id="c6f90-145">The Planning Tool reduces this complexity by generating a report that defines in detail all firewall requirements, based on the designer's input criteria.</span></span> <span data-ttu-id="c6f90-146">IT 防火牆管理員將能使用此報告來設定及定義必要的規則。</span><span class="sxs-lookup"><span data-stu-id="c6f90-146">The IT firewall administrator will be able to use this report to configure and define the necessary rules.</span></span>

<span data-ttu-id="c6f90-147">從防火牆管理的角度來看，應仔細檢查報告，以確保現有的防火牆規則沒有任何衝突，且沒有任何原則或程式可能違反。</span><span class="sxs-lookup"><span data-stu-id="c6f90-147">From the standpoint of firewall management, the report should be carefully reviewed to make sure that there are no conflicts with exiting firewall rules and that there are no policies or procedures that might be violated.</span></span>

![防火牆管理員報告](../../media/Firewall_Report_Admin_Report.png)

## <a name="review-the-dns-report"></a><span data-ttu-id="c6f90-149">查看 DNS 報告</span><span class="sxs-lookup"><span data-stu-id="c6f90-149">Review the DNS Report</span></span>
<span data-ttu-id="c6f90-150"><a name="DNS_Report"> </a></span><span class="sxs-lookup"><span data-stu-id="c6f90-150"><a name="DNS_Report"> </a></span></span>

<span data-ttu-id="c6f90-151">DNS 報告是系統管理員報告的一部分，詳細說明內部、週邊及外部網路中的網域名稱系統（DNS）的所有建議和已知專案。</span><span class="sxs-lookup"><span data-stu-id="c6f90-151">The DNS Report, which is part of the Administrator Report, details all of the recommended and known entries for the Domain Name System (DNS) in the internal, perimeter, and external networks.</span></span> <span data-ttu-id="c6f90-152">如果設計工具已完成對 network 圖表的編輯，且所有 IP 位址及完整功能變數名稱（Fqdn）都定義為其生產值，則 DNS 報告會提供絕佳的配置資源。</span><span class="sxs-lookup"><span data-stu-id="c6f90-152">If the designer has completed the edits to the network diagram, and all IP addresses and fully qualified domain names (FQDNs) are defined to their production values, the DNS Report provides an excellent configuration resource.</span></span> <span data-ttu-id="c6f90-153">此報告也可以做為操作疑難排解檔。</span><span class="sxs-lookup"><span data-stu-id="c6f90-153">This report can also serve as an operational troubleshooting document.</span></span>

![DNS 管理員報告](../../media/DNS_Report_Admin_Report.png)

<span data-ttu-id="c6f90-155">您應該讓您的 DNS 管理小組徹底檢查 DNS 報告，以確保在部署期間不存在可能造成困難的錯誤，或可能會使疑難排解會話複雜化。</span><span class="sxs-lookup"><span data-stu-id="c6f90-155">You should have your DNS management team review the DNS Report thoroughly to make sure that there are no errors that may cause difficulty during deployment or that may complicate a troubleshooting session.</span></span>

## <a name="see-also"></a><span data-ttu-id="c6f90-156">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c6f90-156">See also</span></span>
<span data-ttu-id="c6f90-157"><a name="DNS_Report"> </a></span><span class="sxs-lookup"><span data-stu-id="c6f90-157"><a name="DNS_Report"> </a></span></span>

[<span data-ttu-id="c6f90-158">檢閱管理員報告</span><span class="sxs-lookup"><span data-stu-id="c6f90-158">Reviewing the Administrator Reports</span></span>](https://technet.microsoft.com/library/1dee56a9-a033-4201-9765-e3469bd7d3e3.aspx)
