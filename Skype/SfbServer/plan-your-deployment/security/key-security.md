---
title: 商務用 Skype Server 中的主要安全性功能
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
description: 商務用 Skype Server 包含數個安全性功能，包括伺服器對伺服器驗證、角色型存取控制，以及設定資料的集中式儲存區。
ms.openlocfilehash: bf4b2c9bb96e7180b5da61462db137f0624ea9efa504295336ed05668bde4410
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54329527"
---
# <a name="key-security-features-in-skype-for-business-server"></a>商務用 Skype Server 中的主要安全性功能
 
商務用 Skype Server 包含數個安全性功能，包括伺服器對伺服器驗證、角色型存取控制，以及設定資料的集中式儲存區。 
  
本文供應商務用 Skype Server 安全性的高層次概述。 
  
## <a name="key-security-features-in-skype-for-business-server"></a>商務用 Skype Server 中的主要安全性功能

安全性是非常廣泛的主題。 每個商務用 Skype Server 功能的安全性，以及構成商務用 Skype Server 生態系統的資料庫、服務和硬體。 本文概述商務用 Skype Server 中的一些特別是針對安全性而設計的功能。
  
### <a name="planning-and-design-tools"></a>規劃及設計工具

商務用 Skype Server 提供兩個工具，以協助規劃及設計，並降低誤設定商務用 Skype Server 元件的機率。 
  
- **拓撲規劃工具** 會使大部分的拓撲設計程式自動化。 您可以將規劃工具的結果匯出至拓撲產生器，這是安裝執行商務用 Skype Server 的每一部伺服器所需的工具。
    
- **拓撲** 產生器會將所有設定資訊儲存在中央管理存放區中。
    
如需這些工具的詳細資訊，請參閱[商務用 Skype Server 管理工具](../../management-tools/management-tools.md)。
  
### <a name="central-management-store"></a>Central Management Store

在商務用 Skype Server 中，伺服器和服務的設定資料是中央管理存放區的一部分。 中央管理存放區為定義、設定、維護、管理、描述及操作商務用 Skype Server 部署所需的資料提供了可靠的 schematized 儲存區。 它也驗證資料，以確保設定一致性。 對此設定資料所做的所有變更都會發生在中央管理存放區，消除「不同步」的問題。 
  
資料的唯讀複本會複製到拓撲中的所有伺服器，包括 Edge Server。 複寫是由預設會在網路服務內容下執行的服務所管理，可減少電腦上的簡易使用者的權利和許可權。 
  
### <a name="server-to-server-authentication"></a>Server-to-Server 驗證

在商務用 Skype Server 中，您可以使用「開啟授權」 (OAuth) 通訊協定，在伺服器之間設定驗證。 例如，您可以設定商務用 Skype Server 以執行 Microsoft Exchange Server 2016 的伺服器進行驗證。 商務用 Skype Server 和 Microsoft Exchange Server 的使用 OAuth 通訊協定可以相互信任。 這讓您能夠以無縫的方式整合產品。 如需詳細資訊，請參閱[Manage server to server 驗證 (OAuth) 和夥伴應用程式商務用 Skype Server](../../manage/authentication/server-to-server-and-partner-applications.md)。
  
### <a name="windows-powershell-based-management-and-web-based-management-interface"></a>Windows PowerShell 型管理和以網路為基礎的管理介面

商務用 Skype Server 提供強大的管理介面，在 Windows PowerShell 命令列介面上建立。 它包含管理安全性的 Cmdlet，預設會啟用 Windows PowerShell 安全性功能，讓使用者無法輕易或無意中執行腳本。 這表示軟體預設值設為自動協助最大化安全性，並減少攻擊途徑。 如需商務用 Skype Server 中 Windows PowerShell 管理支援的詳細資訊，請參閱[商務用 Skype Server 管理命令](../../manage/management-shell.md)介面。 
  
### <a name="role-based-access-control-rbac"></a>角色型存取控制 (RBAC)

商務用 Skype Server 提供以角色為基礎的存取控制 (RBAC) ，可讓您委派管理工作，同時維持高安全性標準。 您可以使用 RBAC 遵循「最低許可權」的原則，讓使用者只會獲得其工作所需的系統管理許可權。 商務用 Skype Server 可讓您建立新的角色，以及修改現有角色的能力。 
  
## <a name="network-address-translation-nat"></a>網路位址轉譯 (NAT) 

商務用 Skype Server 不支援在 Edge server 的內部介面上使用網路位址轉譯 (NAT) ，但它不支援將 Access edge service、Web 會議 Edge service 及 A/V Edge service 的外部介面放在路由器或防火牆後面，可對單一及調整式合併 Edge Server 拓撲執行網路位址轉譯 (NAT) 。 硬體負載平衡器背後的多部 Edge Server 無法使用 NAT。 如果有多部 Edge Server 在其外部介面上使用 NAT，則需要網域名稱系統 (DNS) 負載平衡。 反過來，使用 DNS 負載平衡可讓您減少 Edge Server 集區中每一 Edge Server 的公用 IP 位址數目。 如需詳細資訊，請參閱[商務用 Skype Server 中的 Edge Server 案例](../../plan-your-deployment/edge-server-deployments/scenarios.md)。
  
> [!NOTE]
> 如果您與使用 Microsoft Office 通訊伺服器2007部署的企業同盟，且您需要在您的企業和同盟企業之間使用音訊/視頻，則埠需求將是部署之舊版伺服器的埠需求。 例如，必須針對這兩種企業開啟這些舊版本所需的埠範圍，直到同盟協力廠商伺服器將其 Edge server 升級為商務用 Skype Server 為止。 在這個階段，您可以根據新設定來檢查和縮短埠需求。 
  
## <a name="simplified-certificates-for-edge-servers"></a>簡化 Edge Server 的憑證

部署嚮導可自動將主體名稱填入 (SNs) 和主體替代名稱 (SANs) ，以減少包含不必要的可能不安全專案的可能性。
  
## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a>可信賴的計算安全性開發生命週期 (SDL) 

商務用 Skype Server 會以符合[Microsoft 可信賴計算安全性開發生命週期](/previous-versions/ms995349(v=msdn.10)) (SDL) 所設計和開發。
  
- **以設計為可信** 建立更安全的整合通訊系統的第一步是設計威脅模型，並在設計時測試每項功能。 此外，Microsoft 會在設計行為以外執行測試，以找出意外產品行為所產生的安全性弱點。 程式碼撰寫和慣例已內建許多安全性相關的改進。 組建時間工具會在將程式碼存回最終產品之前，偵測緩衝區溢位及其他潛在安全性威脅。 當然，不可能針對所有未知的安全性威脅進行設計。 沒有任何系統可以保證絕對的安全性。 不過，因為產品開發會從開始起起安全的設計原則，所以商務用 Skype Server 將業界標準安全性技術併入其架構的基礎部分。
    
- **預設為可信** 預設會加密商務用 Skype Server 中的網路通訊。 由於所有伺服器都使用憑證及 Kerberos 驗證、TLS、安全 Real-Time 傳輸通訊協定 (SRTP) 和其他業界標準加密技術，包括128位的進階加密標準 (AES) 加密，實際上所有商務用 Skype Server 資料在網路上都受到保護。 此外，以角色為基礎的存取控制可讓您部署執行商務用 Skype Server 的伺服器，讓每個伺服器角色只執行服務，而且只會有與這些服務相關的許可權，這些都適用于伺服器角色。
    
- **信任的部署** 所有商務用 Skype Server 檔都包含最佳作法和建議，可協助您決定及設定部署的最佳安全性層級，並評估啟用非預設選項的安全性風險。
