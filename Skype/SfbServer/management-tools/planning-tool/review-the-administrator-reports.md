---
title: 在商務用 Skype Server 2015 中查看系統管理員報告
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 22d480ea-cd64-4d09-99fe-96e997570844
description: 系統管理員報告包含部署和作業的詳細資訊。 會根據設計網站中標示的選取專案產生報告。 設計師可以編輯網路圖，以及定義伺服器、集區和負載平衡器的完整 IP 位址和完整網域名稱 (FQDN)，提升系統管理員報告的價值。
ms.openlocfilehash: e2a30e27b5b1928dacc36e5592033090484f065a
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60766291"
---
# <a name="review-the-administrator-reports-in-skype-for-business-server-2015"></a>在商務用 Skype Server 2015 中查看系統管理員報告

系統管理員報告包含部署和作業的詳細資訊。 會根據 **設計網站** 中標示的選取專案產生報告。 設計師可以編輯網路圖，以及定義伺服器、集區和負載平衡器的完整 IP 位址和完整網域名稱 (FQDN)，提升系統管理員報告的價值。

管理員報告功能可讓您：

- [審閱摘要報告](review-the-administrator-reports.md#Summary_report)

- [查看憑證報告](review-the-administrator-reports.md#Certificates_Report)

- [複查防火牆報告](review-the-administrator-reports.md#Firewall_report)

- [複查 DNS 報告](review-the-administrator-reports.md#DNS_Report)

## <a name="review-the-summary-report"></a>審閱摘要報告
<a name="Summary_report"> </a>

商務用 Skype 管理員報告是四個重要報告中的第一個，可將您的設計詳細記錄。 在此報告中的資訊，以及其他三個相關聯的報告，對您的資訊技術 Teams 非常有用：

![一般摘要管理員報告。](../../media/General_Summary_Report_Admin_Report.png)

摘要報告列出與 Edge 網路相關的一般設定資訊。 會記錄位置、完整功能變數名稱 (FQDN) 和 IP 位址、網路類型，以及特定角色特有的批註。

設計人員和部署、管理及維護基礎結構的每一個小組，都應該檢查摘要報告的準確性，並確認至少有錯誤。

您也可以查看更詳細的報告：

- 憑證報告

- 防火牆報告

- DNS 報告

## <a name="review-the-certificates-report"></a>查看憑證報告
<a name="Certificates_Report"> </a>

憑證報告包含建議的商務用 Skype Server 2015 部署中所需的所有憑證。 規劃工具會為所輸入的主旨名稱和主體替代名稱提供帳戶。 未編輯的預設文字可能代表負責要求及簽發憑證的小組潛在挑戰。 憑證資訊同時包含憑證一般發行來源的相關資訊。 如果基礎結構不存在內部公開金鑰基礎結構 (PKI)，則所有憑證皆可透過公開憑證提供者要求。 報告中的「擴充金鑰使用方法 (EKU)」與「指派給」欄位對於了解每一個憑證的用途及歸屬位置非常有用。

![憑證系統管理員報告。](../../media/Certificates_Report_Admin_Report.png)

請認真檢查，並務必瞭解部署中每個憑證的使用和用途。 如果有關于憑證用途的問題，請判斷哪個伺服器或服務與哪個服務交談。 商務用 Skype Server 2015 中的憑證是用於兩個主要目的：

- 相互傳輸層安全性 (MTLS) -每個通訊中的電腦都會呈現憑證，證明其身分識別至另一部電腦。 這稱為「伺服器驗證」。 在每一部電腦信任另一部電腦的身分識別之前，無法開始通訊。

- 加密加密 (安全通訊端層（或 SSL）和傳輸層安全性，或 TLS) 是協助保護通訊安全的重要方式，協助確保隱私權，以及建立信任的通訊和共同作業系統。

## <a name="review-the-firewall-report"></a>複查防火牆報告
<a name="Firewall_report"> </a>

商務用 Skype Server 2015 有可能的一組可能很複雜的防火牆規則。 規劃工具會根據設計人員的輸入準則，產生定義以詳細說明所有防火牆需求的報告，以降低這項複雜性。 IT 防火牆管理員可以運用這項報告，設定與定義必要的規則。

從防火牆管理的觀點來看，應仔細檢查報告，確定沒有任何與現有防火牆規則的衝突，而且沒有任何可能違反的原則或程式。

![防火牆管理員報告。](../../media/Firewall_Report_Admin_Report.png)

## <a name="review-the-dns-report"></a>複查 DNS 報告
<a name="DNS_Report"> </a>

DNS 報告是系統管理員報告的一部分，詳述內部、周邊及外部網路中，網域名稱系統 (DNS) 的所有建議和已知專案。 如果設計者已完成對 [網狀圖] 的編輯，而且所有的 IP 位址和完整功能變數名稱 (Fqdn) 會定義為其實際執行值，則 DNS 報告會提供極佳的設定資源。 這份報告也可以做為運作疑難排解檔。

![DNS 管理員報告。](../../media/DNS_Report_Admin_Report.png)

您應該讓 DNS 管理小組徹底複查 DNS 報告，以確保在部署期間沒有任何可能造成困難的錯誤，或可能使疑難排解會話複雜化的錯誤。

## <a name="see-also"></a>另請參閱
<a name="DNS_Report"> </a>

[檢閱管理員報告](/previous-versions/office/lync-server-2013/lync-server-2013-reviewing-the-administrator-reports)