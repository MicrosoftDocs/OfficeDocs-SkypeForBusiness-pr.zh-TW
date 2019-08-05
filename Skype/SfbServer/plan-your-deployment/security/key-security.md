---
title: 商務用 Skype Server 中的主要安全性功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
description: 商務用 Skype 伺服器包含數種安全性功能, 包括伺服器到伺服器驗證、以角色為基礎的存取控制, 以及集中式儲存配置資料。
ms.openlocfilehash: cd86d1ac404cd2fe487f6f9369cc73df0d72c52f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192942"
---
# <a name="key-security-features-in-skype-for-business-server"></a>商務用 Skype Server 中的主要安全性功能
 
商務用 Skype 伺服器包含數種安全性功能, 包括伺服器到伺服器驗證、以角色為基礎的存取控制, 以及集中式儲存配置資料。 
  
這篇文章供應商務用 Skype Server 安全性的高層次概覽。 
  
## <a name="key-security-features-in-skype-for-business-server"></a>商務用 Skype Server 中的主要安全性功能

安全性是一個非常廣泛的主題。 安全性達到商務用 Skype Server 的每項功能, 以及組成商務用 Skype Server 生態系統的資料庫、服務和硬體。 本文將概述商務用 Skype Server 中的部分功能, 特別是針對安全性設計的。
  
### <a name="planning-and-design-tools"></a>規劃和設計工具

商務用 skype 伺服器提供兩種工具, 可協助規劃及設計並減少錯誤地設定商務用 Skype 伺服器元件的機率。 
  
- **拓撲規劃工具**自動化了許多拓撲設計程式。 您可以將規劃工具的結果匯出至 [拓撲建立器], 這是安裝執行商務用 Skype Server 的每個伺服器所需的工具。
    
- **拓撲**建立器會將所有配置資訊儲存在中央管理儲存區中。
    
如需這些工具的詳細資訊, 請參閱[商務用 Skype Server 管理工具](../../management-tools/management-tools.md)。
  
### <a name="central-management-store"></a>中央管理存放區

在商務用 Skype Server 中, 伺服器與服務的設定資料是集中式管理儲存體的一部分。 [中央管理] 商店提供資料的強健、schematized 儲存, 以定義、設定、維護、管理、描述及操作商務用 Skype Server 部署。 它也會驗證資料, 以確保配置一致性。 此設定資料的所有變更都會出現在中央管理商店, 消除「不同步」問題。 
  
唯讀複本會將資料複製到拓撲中的所有伺服器, 包括 Edge 伺服器和 Survivable 分支裝置。 複製是由預設會在網路服務內容下執行的服務所管理, 可減少電腦上簡單使用者的權利和許可權。 
  
### <a name="server-to-server-authentication"></a>伺服器對伺服器驗證

在商務用 Skype Server 中, 您可以使用開啟授權 (OAuth) 通訊協定, 在伺服器之間設定驗證。 例如, 您可以將商務用 Skype 伺服器設定為使用執行 Microsoft Exchange Server 2016 的伺服器進行驗證。 使用 OAuth 通訊協定, 商務用 Skype 伺服器與 Microsoft Exchange 伺服器可以相互信任。 這能讓您以流暢的方式整合產品。 如需詳細資訊, 請參閱[管理商務用 Skype server 中的伺服器到伺服器驗證 (OAuth) 和合作夥伴應用程式](../../manage/authentication/server-to-server-and-partner-applications.md)。
  
### <a name="windows-powershell-based-management-and-web-based-management-interface"></a>Windows PowerShell 式管理和網路式管理介面

商務用 Skype 伺服器提供功能強大的管理介面 (在 Windows PowerShell 命令列介面上建立)。 它包含管理安全性的 Cmdlet, 而且預設會啟用 Windows PowerShell 安全性功能, 讓使用者不會輕易或無意中執行腳本。 這表示軟體預設值會設定為自動協助最大化安全性並減少攻擊途徑。 如需在商務用 Skype Server 中的 Windows PowerShell 管理支援的詳細資訊, 請參閱[商務用 Skype Server 管理命令](../../manage/management-shell.md)介面。 
  
### <a name="role-based-access-control-rbac"></a>以角色為基礎的存取控制 (RBAC)

商務用 Skype 伺服器提供以角色為基礎的存取控制 (RBAC), 可讓您委派管理工作, 同時維持高安全性的標準。 您可以使用 RBAC 遵循「最低許可權」的原則, 在此原則中, 使用者只會得到他們工作所需的管理許可權。 商務用 Skype Server 提供建立新角色的功能, 以及修改現有角色的功能。 
  
## <a name="network-address-translation-nat"></a>網路位址轉譯 (NAT)

商務用 Skype Server 不支援在 Edge 伺服器的內部介面上使用網路位址轉譯 (NAT), 但支援將存取邊緣服務、網路會議 Edge 服務和 A/V 邊緣服務的外部介面放在外在路由器或防火牆之後, 對於單一和縮放的合併邊緣伺服器拓撲, 都執行網路位址轉譯 (NAT)。 在硬體負載平衡器後的多個邊緣伺服器無法使用 NAT。 如果有多個邊緣伺服器在其外部介面上使用 NAT, 則需要網功能變數名稱稱系統 (DNS) 負載平衡。 接著, 您可以使用 DNS 負載平衡, 在 Edge 伺服器池中減少每個邊緣伺服器的公用 IP 位址數目。 如需詳細資訊, 請參閱[商務用 Skype server 中的邊緣伺服器案例](../../plan-your-deployment/edge-server-deployments/scenarios.md)。
  
> [!NOTE]
> 如果您是與已安裝 Microsoft Office 通訊伺服器2007部署的企業聯盟, 而且您需要在企業與同盟企業之間使用音訊/視頻, 則埠需求就會是舊版的 Edge 伺服器已部署。 例如, 在聯盟合作夥伴將其 Edge 伺服器升級到商務用 Skype 伺服器之前, 必須為這兩個企業開啟這些較舊版本所需的埠範圍。 此時, 您可以根據新設定來審查並減少埠需求。 
  
## <a name="simplified-certificates-for-edge-servers"></a>簡化的邊緣伺服器憑證

[部署嚮導] 可自動填入消費者名稱 (SNs) 和消費者備用名稱 (San), 減少包括不必要和可能不安全的專案的可能性。
  
## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a>可信計算安全性開發週期 (SDL)

商務用 Skype Server 的設計與開發符合[Microsoft 高可信計算安全性開發週期](https://go.microsoft.com/fwlink/p/?linkid=68761)(SDL)。
  
- **根據設計信任**建立更安全的整合通訊系統的第一個步驟是設計威脅模型, 並測試每個功能的設計。 此外, Microsoft 還會在設計的行為以外執行測試, 以找出意外產品行為所產生的安全性漏洞。 編碼程式與做法內建了多個安全性相關的改良功能。 在將程式碼簽入最終產品之前, 組建時間工具會偵測緩衝區溢位及其他潛在安全性威脅。 當然, 可能無法針對所有未知的安全性威脅進行設計。 任何系統都不能保證完整的安全性。 不過, 由於產品開發採用了從開始、商務用 Skype 伺服器的安全設計原則, 因此將業界標準安全技術納入其架構的基本部分。
    
- **預設為可信**根據預設, 商務用 Skype Server 中的網路通訊是經過加密的。 因為所有伺服器都使用憑證和 Kerberos 驗證、TLS、安全的即時傳輸通訊協定 (SRTP), 以及其他業界標準的加密技術, 包括128位進階加密標準 (AES) 加密, 幾乎所有 Skype 都適用于商務伺服器資料在網路上受到保護。 此外, 角色式存取控制能讓您部署執行商務用 Skype Server 的伺服器, 讓每個伺服器角色只執行服務, 而且只有與這些服務相關聯的許可權, 這些都適用于伺服器角色。
    
- **受部署信任**所有商務用 Skype Server 檔都包含最佳做法和建議, 可協助您判斷並設定您的部署的最佳安全等級, 並評估啟用非預設選項的安全性風險。
    

