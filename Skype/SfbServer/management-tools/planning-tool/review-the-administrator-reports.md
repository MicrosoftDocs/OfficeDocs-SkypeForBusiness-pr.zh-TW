---
title: 在商務用 Skype Server 2015 中複查管理員報告
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 系統管理員報告包含部署和作業的詳細資訊。 會根據設計網站中標示的選取專案產生報告。 設計師可以編輯網路圖，以及定義伺服器、集區和負載平衡器的完整 IP 位址和完整網域名稱 (FQDN)，提升系統管理員報告的價值。
ms.openlocfilehash: b8c18dcfef28ac93e8c2036fee7f7b105f5c69bd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823343"
---
# <a name="review-the-administrator-reports-in-skype-for-business-server-2015"></a><span data-ttu-id="eac9c-105">在商務用 Skype Server 2015 中複查管理員報告</span><span class="sxs-lookup"><span data-stu-id="eac9c-105">Review the Administrator Reports in Skype for Business Server 2015</span></span>

<span data-ttu-id="eac9c-106">系統管理員報告包含部署和作業的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="eac9c-106">The Administrator Reports are detailed information for deployment and operations.</span></span> <span data-ttu-id="eac9c-107">會根據 **設計網站** 中標示的選取專案產生報告。</span><span class="sxs-lookup"><span data-stu-id="eac9c-107">The reports are generated based on the selections marked in **Design Sites**.</span></span> <span data-ttu-id="eac9c-108">設計師可以編輯網路圖，以及定義伺服器、集區和負載平衡器的完整 IP 位址和完整網域名稱 (FQDN)，提升系統管理員報告的價值。</span><span class="sxs-lookup"><span data-stu-id="eac9c-108">The designer can further add value to the Administrator Reports by editing the network diagrams and defining the complete IP addresses and fully qualified domain names (FQDNs) for servers, pools, and load balancers.</span></span>

<span data-ttu-id="eac9c-109">管理員報告功能可讓您：</span><span class="sxs-lookup"><span data-stu-id="eac9c-109">The Administrator reports feature allows you to:</span></span>

- [<span data-ttu-id="eac9c-110">審閱摘要報告</span><span class="sxs-lookup"><span data-stu-id="eac9c-110">Review the Summary Report</span></span>](review-the-administrator-reports.md#Summary_report)

- [<span data-ttu-id="eac9c-111">查看憑證報告</span><span class="sxs-lookup"><span data-stu-id="eac9c-111">Review the Certificates Report</span></span>](review-the-administrator-reports.md#Certificates_Report)

- [<span data-ttu-id="eac9c-112">複查防火牆報告</span><span class="sxs-lookup"><span data-stu-id="eac9c-112">Review the Firewall Report</span></span>](review-the-administrator-reports.md#Firewall_report)

- [<span data-ttu-id="eac9c-113">複查 DNS 報告</span><span class="sxs-lookup"><span data-stu-id="eac9c-113">Review the DNS Report</span></span>](review-the-administrator-reports.md#DNS_Report)

## <a name="review-the-summary-report"></a><span data-ttu-id="eac9c-114">審閱摘要報告</span><span class="sxs-lookup"><span data-stu-id="eac9c-114">Review the Summary Report</span></span>
<span data-ttu-id="eac9c-115"><a name="Summary_report"> </a></span><span class="sxs-lookup"><span data-stu-id="eac9c-115"><a name="Summary_report"> </a></span></span>

<span data-ttu-id="eac9c-116">商務用 Skype 系統管理員報告是四個重要報告中的第一個，以詳細記錄您的設計。</span><span class="sxs-lookup"><span data-stu-id="eac9c-116">The Skype for Business Administrator Report is the first of four valuable reports that document your design in detail.</span></span> <span data-ttu-id="eac9c-117">在此報告中的資訊，以及其他三個相關聯的報告，對您的資訊技術小組非常有用：</span><span class="sxs-lookup"><span data-stu-id="eac9c-117">The information in this report, and the other three associated reports, is useful for your Information Technology Teams:</span></span>

![一般摘要管理員報告](../../media/General_Summary_Report_Admin_Report.png)

<span data-ttu-id="eac9c-119">摘要報告列出與 Edge 網路相關的一般設定資訊。</span><span class="sxs-lookup"><span data-stu-id="eac9c-119">The Summary Report lists general configuration information associated with your Edge network.</span></span> <span data-ttu-id="eac9c-120">會記錄位置、完整功能變數名稱 (FQDN) 和 IP 位址、網路類型，以及特定角色特有的批註。</span><span class="sxs-lookup"><span data-stu-id="eac9c-120">The location, fully qualified domain name (FQDN) and IP address, type of network, and comments specific to a given role are documented.</span></span>

<span data-ttu-id="eac9c-121">設計人員和部署、管理及維護基礎結構的每一個小組，都應該檢查摘要報告的準確性，並確認至少有錯誤。</span><span class="sxs-lookup"><span data-stu-id="eac9c-121">The designer and each of the teams that will deploy, manage, and maintain the infrastructure should review the summary report for accuracy and to make sure that errors are at a minimum.</span></span>

<span data-ttu-id="eac9c-122">您也可以查看更詳細的報告：</span><span class="sxs-lookup"><span data-stu-id="eac9c-122">You can also view more detailed reports:</span></span>

- <span data-ttu-id="eac9c-123">憑證報告</span><span class="sxs-lookup"><span data-stu-id="eac9c-123">Certificates Report</span></span>

- <span data-ttu-id="eac9c-124">防火牆報告</span><span class="sxs-lookup"><span data-stu-id="eac9c-124">Firewall Report</span></span>

- <span data-ttu-id="eac9c-125">DNS 報告</span><span class="sxs-lookup"><span data-stu-id="eac9c-125">DNS Report</span></span>

## <a name="review-the-certificates-report"></a><span data-ttu-id="eac9c-126">查看憑證報告</span><span class="sxs-lookup"><span data-stu-id="eac9c-126">Review the Certificates Report</span></span>
<span data-ttu-id="eac9c-127"><a name="Certificates_Report"> </a></span><span class="sxs-lookup"><span data-stu-id="eac9c-127"><a name="Certificates_Report"> </a></span></span>

<span data-ttu-id="eac9c-128">憑證報告包含建議的商務用 Skype Server 2015 部署中所需的所有憑證。</span><span class="sxs-lookup"><span data-stu-id="eac9c-128">The Certificates Report contains all certificates that are required in the recommended Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="eac9c-129">規劃工具會為所輸入的主旨名稱和主體替代名稱提供帳戶。</span><span class="sxs-lookup"><span data-stu-id="eac9c-129">The Planning Tool accounts for the subject names and subject alternative names that are entered.</span></span> <span data-ttu-id="eac9c-130">未編輯的預設文字可能代表負責要求及簽發憑證的小組潛在挑戰。</span><span class="sxs-lookup"><span data-stu-id="eac9c-130">Default text that is left unedited may represent a potential challenge for the team responsible for requesting and issuing the certificates.</span></span> <span data-ttu-id="eac9c-131">憑證資訊同時包含憑證一般發行來源的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="eac9c-131">Certificate information also contains information about where the certificate can typically be issued from.</span></span> <span data-ttu-id="eac9c-132">如果基礎結構不存在內部公開金鑰基礎結構 (PKI)，則所有憑證皆可透過公開憑證提供者要求。</span><span class="sxs-lookup"><span data-stu-id="eac9c-132">If the infrastructure does not have an internal public key infrastructure (PKI) in place, all certificates can be requested through a public certificate provider.</span></span> <span data-ttu-id="eac9c-133">報告中的「擴充金鑰使用方法 (EKU)」與「指派給」欄位對於了解每一個憑證的用途及歸屬位置非常有用。</span><span class="sxs-lookup"><span data-stu-id="eac9c-133">Extended key usages (EKU) and Assign To fields in the report are very helpful in understanding what the purpose and location for each certificate should be.</span></span>

![憑證管理員報告](../../media/Certificates_Report_Admin_Report.png)

<span data-ttu-id="eac9c-135">請認真檢查，並務必瞭解部署中每個憑證的使用和用途。</span><span class="sxs-lookup"><span data-stu-id="eac9c-135">Carefully review, and be sure to understand, the use and purpose of each certificate in the deployment.</span></span> <span data-ttu-id="eac9c-136">如果有關于憑證用途的問題，請判斷哪個伺服器或服務與哪個服務交談。</span><span class="sxs-lookup"><span data-stu-id="eac9c-136">If there is a question about what a certificate does, determine which server or service is talking to what.</span></span> <span data-ttu-id="eac9c-137">商務用 Skype Server 2015 中的憑證是用於兩個主要目的：</span><span class="sxs-lookup"><span data-stu-id="eac9c-137">Certificates in Skype for Business Server 2015 are used for two primary purposes:</span></span>

- <span data-ttu-id="eac9c-138">相互傳輸層安全性 (MTLS) -每個通訊中的電腦都會呈現憑證，證明其身分識別至另一部電腦。</span><span class="sxs-lookup"><span data-stu-id="eac9c-138">Mutual Transport Layer Security (MTLS) - The computers involved in the communication each present a certificate that proves their identity to another computer.</span></span> <span data-ttu-id="eac9c-139">這稱為「伺服器驗證」。</span><span class="sxs-lookup"><span data-stu-id="eac9c-139">This is known as server authentication.</span></span> <span data-ttu-id="eac9c-140">在每一部電腦信任另一部電腦的身分識別之前，無法開始通訊。</span><span class="sxs-lookup"><span data-stu-id="eac9c-140">Communication cannot begin until each computer trusts the other computer's identity.</span></span>

- <span data-ttu-id="eac9c-141">加密加密 (安全通訊端層（或 SSL）和傳輸層安全性，或 TLS) 是協助保護通訊安全的重要方式，協助確保隱私權，以及建立信任的通訊和共同作業系統。</span><span class="sxs-lookup"><span data-stu-id="eac9c-141">Encryption - Encryption (Secure Sockets Layer, or SSL, and Transport Layer Security, or TLS) is a critical means to help secure communications, help ensure privacy, and to create a trusted communications and collaboration system.</span></span>

## <a name="review-the-firewall-report"></a><span data-ttu-id="eac9c-142">複查防火牆報告</span><span class="sxs-lookup"><span data-stu-id="eac9c-142">Review the Firewall Report</span></span>
<span data-ttu-id="eac9c-143"><a name="Firewall_report"> </a></span><span class="sxs-lookup"><span data-stu-id="eac9c-143"><a name="Firewall_report"> </a></span></span>

<span data-ttu-id="eac9c-144">商務用 Skype Server 2015 有一組可能很複雜的防火牆規則。</span><span class="sxs-lookup"><span data-stu-id="eac9c-144">Skype for Business Server 2015 has a potentially complex set of firewall rules.</span></span> <span data-ttu-id="eac9c-145">規劃工具會根據設計人員的輸入準則，產生定義以詳細說明所有防火牆需求的報告，以降低這項複雜性。</span><span class="sxs-lookup"><span data-stu-id="eac9c-145">The Planning Tool reduces this complexity by generating a report that defines in detail all firewall requirements, based on the designer's input criteria.</span></span> <span data-ttu-id="eac9c-146">IT 防火牆管理員可以運用這項報告，設定與定義必要的規則。</span><span class="sxs-lookup"><span data-stu-id="eac9c-146">The IT firewall administrator will be able to use this report to configure and define the necessary rules.</span></span>

<span data-ttu-id="eac9c-147">從防火牆管理的觀點來看，應仔細檢查報告，確定沒有任何與現有防火牆規則的衝突，而且沒有任何可能違反的原則或程式。</span><span class="sxs-lookup"><span data-stu-id="eac9c-147">From the standpoint of firewall management, the report should be carefully reviewed to make sure that there are no conflicts with exiting firewall rules and that there are no policies or procedures that might be violated.</span></span>

![防火牆管理員報告](../../media/Firewall_Report_Admin_Report.png)

## <a name="review-the-dns-report"></a><span data-ttu-id="eac9c-149">複查 DNS 報告</span><span class="sxs-lookup"><span data-stu-id="eac9c-149">Review the DNS Report</span></span>
<span data-ttu-id="eac9c-150"><a name="DNS_Report"> </a></span><span class="sxs-lookup"><span data-stu-id="eac9c-150"><a name="DNS_Report"> </a></span></span>

<span data-ttu-id="eac9c-151">DNS 報告是系統管理員報告的一部分，詳述內部、周邊及外部網路中，網域名稱系統 (DNS) 的所有建議和已知專案。</span><span class="sxs-lookup"><span data-stu-id="eac9c-151">The DNS Report, which is part of the Administrator Report, details all of the recommended and known entries for the Domain Name System (DNS) in the internal, perimeter, and external networks.</span></span> <span data-ttu-id="eac9c-152">如果設計者已完成對 [網狀圖] 的編輯，而且所有的 IP 位址和完整功能變數名稱 (Fqdn) 會定義為其實際執行值，則 DNS 報告會提供極佳的設定資源。</span><span class="sxs-lookup"><span data-stu-id="eac9c-152">If the designer has completed the edits to the network diagram, and all IP addresses and fully qualified domain names (FQDNs) are defined to their production values, the DNS Report provides an excellent configuration resource.</span></span> <span data-ttu-id="eac9c-153">這份報告也可以做為運作疑難排解檔。</span><span class="sxs-lookup"><span data-stu-id="eac9c-153">This report can also serve as an operational troubleshooting document.</span></span>

![DNS 管理員報告](../../media/DNS_Report_Admin_Report.png)

<span data-ttu-id="eac9c-155">您應該讓 DNS 管理小組徹底複查 DNS 報告，以確保在部署期間沒有任何可能造成困難的錯誤，或可能使疑難排解會話複雜化的錯誤。</span><span class="sxs-lookup"><span data-stu-id="eac9c-155">You should have your DNS management team review the DNS Report thoroughly to make sure that there are no errors that may cause difficulty during deployment or that may complicate a troubleshooting session.</span></span>

## <a name="see-also"></a><span data-ttu-id="eac9c-156">另請參閱</span><span class="sxs-lookup"><span data-stu-id="eac9c-156">See also</span></span>
<span data-ttu-id="eac9c-157"><a name="DNS_Report"> </a></span><span class="sxs-lookup"><span data-stu-id="eac9c-157"><a name="DNS_Report"> </a></span></span>

[<span data-ttu-id="eac9c-158">檢閱管理員報告</span><span class="sxs-lookup"><span data-stu-id="eac9c-158">Reviewing the Administrator Reports</span></span>](https://technet.microsoft.com/library/1dee56a9-a033-4201-9765-e3469bd7d3e3.aspx)
