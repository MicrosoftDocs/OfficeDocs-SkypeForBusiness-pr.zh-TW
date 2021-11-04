---
title: 在商務用 Skype Server 2015 中安裝規劃工具
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
ms.assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
description: 在您使用商務用 Skype Server 2015 規劃工具開始設計及規劃商務用 Skype Server 2015 基礎結構之前，您必須先安裝規劃工具。 規劃工具不需要部署到屬於您計畫安裝商務用 Skype Server 2015 的網域或基礎結構中的工作站或伺服器上。 規劃工具附帶的讀我檔案詳細說明安裝及使用此工具的重要資訊。 為了清楚起見，自述檔中的部分資訊是重複的。
ms.openlocfilehash: b476d5d39515fe14d3f13a3ee9dc0c5b5298fdc1
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60756882"
---
# <a name="install-the-planning-tool-in-skype-for-business-server-2015"></a>在商務用 Skype Server 2015 中安裝規劃工具

在您使用商務用 Skype Server 2015 規劃工具開始設計及規劃商務用 Skype Server 2015 基礎結構之前，您必須先安裝規劃工具。 規劃工具不需要部署到屬於您計畫安裝商務用 Skype Server 2015 的網域或基礎結構中的工作站或伺服器上。 規劃工具附帶的讀我檔案詳細說明安裝及使用此工具的重要資訊。 為了清楚起見，自述檔中的部分資訊是重複的。

> [!IMPORTANT]
> 規劃工具需要安裝要安裝該工具之電腦的系統管理員權利和許可權的使用者。

規劃工具的安裝及作業支援的作業系統包括：

- Windows 10

- Windows 8

- Windows 8.1

- Windows Server 2012

- Windows Server 2012 R2

- Windows 7、32位版本

- Windows 7、64位 edition 使用 Win32 上 Windows (WOW) 

- Windows伺服器 2008 R2，使用 WOW

此外，規劃工具需要 Microsoft .NET Framework 4.5。

符合預先安裝需求之後，即可安裝規劃工具。



## <a name="to-install-the-planning-tool"></a>安裝規劃工具

1. 以 Administrators 群組成員的身分登入本機電腦。

2. 使用 Windows Explorer 或命令視窗，找到您下載規劃工具安裝檔的目錄。

3. 找出 SkypeForBusinessPlanningTool.msi。 在 Windows Explorer 中，按兩下檔案。 在命令視窗中，輸入檔案名，然後按 **enter** 執行該檔案。

4. 在 [**商務用 Skype Server 2015，規劃工具安裝精靈]** 的 [歡迎] 頁面上，按 **[下一步]**。

5. 檢查 **End-User 授權合約**，如果您選擇接受授權合約中的使用條款，請選取 [ **我接受授權合約中的條款** ]，然後按 **[下一步]**。

6. 選擇安裝規劃工具檔案的位置。 預設位置是 (x86) \ 商務用 Skype Server 2015 \ 規劃工具 C:\Program 檔案。 若要變更安裝位置，請按一下 [ **變更**]。 在 [ **變更目的地資料夾**] 中，流覽或輸入要安裝盤案的位置，按一下 **[確定]**，然後按 **[下一步**]。

7. 安裝程式現在已準備好安裝規劃工具。 按一下 [ **安裝** ] 以開始安裝程式。

8. 安裝會開始，並會顯示進度。 安裝順利完成後，按一下 **[完成]**。

9. 規劃工具可供使用。

## <a name="optional-software"></a>選用軟體
<a name="Optional_Software"> </a>

商務用 Skype Server 2015 規劃工具的設計目的是要匯出至 Microsoft Excel 和 Microsoft Visio。 雖然不需要在規劃工具作業時執行這些應用程式，但是會為部署和設計的檔增加重要的價值。

### <a name="microsoft-excel"></a>Microsoft Excel

將您的設計匯出為 Microsoft Excel 會在試算表中建立顯示七個索引標籤的報告：

- 摘要-顯示網站設定的資訊，包括使用者計數、容量設定和伺服器設定檔資訊。

- 硬體設定檔-針對拓撲中指定的伺服器（包括 CPU、記憶體、磁片及網路介面），顯示建議硬體設定的報告。 此外，也包含伺服器元件的數量和建議規格。 此外，每個伺服器都是由網站定義，以透過網站提供伺服器需求的完整標記法。

- 埠需求-顯示所有已啟用的埠報告，以及與網域名稱系統負載平衡關聯的 (DNS LB) 和硬體負載平衡器 (HLB) 。 您應該使用此報告規劃您的防火牆和 DNS LB 和 HLB 設定。

- 摘要報告-顯示設定 Edge Server 網路所需之設定的一般摘要。

- 憑證報告-顯示取得執行 Edge Server 所需之憑證所需的主體名稱和主體替代名稱。

- 防火牆報告-顯示外部及內部介面的來源和目的地埠及 IP 位址。

- DNS 報告-顯示您所建立之每個 DNS 專案所需的完整功能變數名稱 (FQDN) 和 IP/VIP 位址。

### <a name="microsoft-visio"></a>Microsoft Visio

將您的設計匯出至 Microsoft Visio 會建立圖表，以供您設定的拓撲和基礎結構的檔目的使用。 您可以編輯並重新排列已匯入的圖表，以符合您的檔需求。 一般的 Visio 圖表會包含：

> [!NOTE]
> 如果您的設計足夠大，需要超過三部前端伺服器，則會為前端集區、前端伺服器、執行 SQL Server 的電腦、IP 位址和 fqdn 建立額外的頁面。

- 已設定商務用 Skype Server 2015 網站的全域拓撲圖表。

- [網站名稱] 索引標籤-顯示具有 Edge Server 的網站設定拓撲，防火牆，公用交換電話網路 (PSTN) 與閘道和內部伺服器部署。 內部部署包含已設定的伺服器及集區，包括前端集區、SQL Server 型伺服器、Active Directory 網域服務、director、Exchange 整合通訊 (UM) 伺服器、Exchange 信箱伺服器、Office Web 應用程式伺服器、轉送伺服器及 Persistent Chat server。

- Edge Network 圖表-詳述具有關聯之 IP 位址和 Fqdn 之 Edge Server 設定的圖表。 此外，也包含 DNS 負載平衡與硬體負載平衡器。 此外，會顯示 Director 和前端伺服器或前端集區，並有相關聯的 DNS LB 或 HLB，以及已指派的 IP 位址 (規劃工具可同時支援 IPv4 和 IPv6 位址) 和 FQDN。

## <a name="see-also"></a>另請參閱
<a name="Optional_Software"> </a>

[安裝規劃工具](/previous-versions/office/lync-server-2013/lync-server-2013-installing-the-planning-tool)