---
title: 在 Lync Server 2013 中安裝選用軟體
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
description: 在您開始使用商務用 Skype Server 2015 規劃工具設計及規劃商務用 Skype Server 2015 基礎結構之前, 您必須先安裝規劃工具。 規劃工具不需要部署到您打算安裝商務用 Skype Server 2015 的網域或基礎結構中的工作站或伺服器。 規劃工具隨附的 Readme 檔案會詳細說明有關安裝及使用工具的重要資訊。 讀我檔案中的部分資訊會在此重複, 以清楚起見。
ms.openlocfilehash: 192eae34bf6cf3fa53be82d8cb4450f960c90314
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188458"
---
# <a name="install-the-planning-tool-in-skype-for-business-server-2015"></a>在 Lync Server 2013 中安裝選用軟體

在您開始使用商務用 Skype Server 2015 規劃工具設計及規劃商務用 Skype Server 2015 基礎結構之前, 您必須先安裝規劃工具。 規劃工具不需要部署到您打算安裝商務用 Skype Server 2015 的網域或基礎結構中的工作站或伺服器。 規劃工具隨附的 Readme 檔案會詳細說明有關安裝及使用工具的重要資訊。 讀我檔案中的部分資訊會在此重複, 以清楚起見。

> [!IMPORTANT]
> 規劃工具必須由使用者在安裝該工具的電腦上擁有系統管理員權利和許可權, 才能安裝。

規劃工具所支援的安裝及作業作業系統包括:

- Windows 10

- Windows 8

- Windows 8。1

- Windows Server 2012

- Windows Server 2012 R2

- Windows 7、32位版本

- Windows 7, 64 在 Win32 上使用 Windows (WOW)

- Windows Server 2008 R2, 使用 WOW

此外, 規劃工具需要 Microsoft .NET Framework 4.5。

在符合預先安裝需求之後, 您就可以安裝規劃工具。



## <a name="to-install-the-planning-tool"></a>若要安裝規劃工具

1. 以管理員群組的成員身分登入本機電腦。

2. 使用 Windows 資源管理器或命令視窗, 找出您下載規劃工具安裝檔的目錄。

3. 找出 SkypeForBusinessPlanningTool。 在 Windows 資源管理器中, 按兩下檔案。 在命令視窗中, 輸入檔案名, 然後按**enter**執行檔案。

4. 在商務用 Skype Server 2015 的 [歡迎] 頁面上, 按一下 [**規劃工具設定向導]**, 然後按 **[下一步**]。

5. 查看 [**使用者授權合約**], 如果您選擇接受授權協定中的使用條款, 請選取 [**我接受授權合約中的條款**], 然後按 **[下一步]**。

6. 選擇安裝規劃工具檔案的位置。 預設位置是商務用 Server 2015 \ 規劃工具的 C:\Program Files (x86) \Skype。 如果您想要變更安裝位置, 請按一下 [**變更**]。 在 [**變更目的地] 資料夾**中, 流覽或輸入安裝盤案的位置, 按一下 **[確定]**, 然後按一下 **[下一步**]。

7. 安裝程式現已準備好安裝規劃工具。 按一下 [**安裝**] 以開始安裝程式。

8. 隨即會啟動安裝, 並顯示進度。 成功完成安裝後, 請按一下 **[完成]**。

9. 規劃工具已就緒, 可供使用。

## <a name="optional-software"></a>選用軟體
<a name="Optional_Software"> </a>

商務用 Skype Server 2015 規劃工具的設計目的是匯出至 Microsoft Excel 和 Microsoft Visio。 雖然這些應用程式不是規劃工具運作所必需的, 但它們確實會為您設計的部署和檔加上重要的價值。

### <a name="microsoft-excel"></a>Microsoft Excel

將您的設計匯出至 Microsoft Excel 時, 會建立一個顯示試算表中七個索引標籤的報表:

- 摘要-顯示網站設定的相關資訊, 包括使用者計數、容量設定和伺服器設定檔資訊。

- 硬體設定檔-顯示在拓撲中指定的伺服器硬體設定 (包括 CPU、記憶體、磁片和網路介面) 的報告。 也包含伺服器元件的數量及建議的規格。 此外, 每個伺服器都是由網站定義, 以根據網站提供伺服器需求的完整表示。

- 埠需求-顯示所有已啟用埠的報告, 以及與網域名稱系統負載平衡 (DNS LB) 與硬體負載平衡器 (HLB) 的關聯。 您應該使用這個報告來規劃您的防火牆和 DNS LB 及 HLB 設定。

- 摘要報告-顯示設定 Edge 伺服器網路所需設定的一般摘要。

- [憑證] 報告-顯示在執行邊緣伺服器所需的憑證所需的消費者名稱和消費者替代名稱。

- Firewall 報告-顯示外部和內部介面的來源和目的地埠和 IP 位址。

- DNS 報告-顯示您所建立之每個 DNS 專案所需的完整功能變數名稱 (FQDN) 和 IP/VIP 位址。

### <a name="microsoft-visio"></a>Microsoft Visio

將您的設計匯出至 Microsoft Visio, 就會建立圖表, 以供您設定的拓撲和基礎結構的檔用途使用。 您可以編輯和重新排列已匯入的圖表, 以符合您的檔需求。 典型的 Visio 圖表會包括:

> [!NOTE]
> 如果您的設計足夠大, 需要超過三個前端伺服器, 則會針對前端池、前端伺服器、執行 SQL Server 的電腦、IP 位址及 Fqdn, 建立額外的頁面。

- [全域拓撲]-已設定商務用 Skype Server 2015 網站的圖表。

- [網站名稱] 索引標籤-顯示含 Edge 伺服器、防火牆、公開交換電話網絡 (PSTN) 與內部伺服器部署的網站配置拓撲。 內部部署由已設定的伺服器和池組成, 包括前端池、SQL Server 服務器、Active Directory 網域服務、控制器、Exchange 整合通訊 (UM) 伺服器、Exchange 信箱伺服器、Office Web Apps 伺服器、中繼伺服器和持續聊天伺服器。

- Edge 網狀圖-詳細說明邊緣伺服器設定與相關聯的 IP 位址和 Fqdn 的圖表。 也包含 DNS 負載平衡與硬體負載平衡器。 此外, 會顯示 [控制器] 與 [前端伺服器] 或 [頂層端] 池, 其中包含相關聯的 DNS LB 或 HLB 以及指派的 IP 位址 (規劃工具支援 IPv4 與 IPv6 位址) 和 FQDN。

## <a name="see-also"></a>另請參閱
<a name="Optional_Software"> </a>

[安裝規劃工具](https://technet.microsoft.com/library/ebdc9e26-4b22-4b02-85b9-7462bcfe7c93.aspx)
