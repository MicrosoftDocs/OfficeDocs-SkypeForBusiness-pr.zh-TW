---
title: Skype 室系統可管理性與工具
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: 若要瞭解 Skype 室系統的管理工具，請閱讀本主題。
ms.openlocfilehash: c9289d3fffa78dd7ffd94fa17784c1b06c2278b1
ms.sourcegitcommit: fa55f9e3690fcca36b530bd13a9eeaa44120b87c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2019
ms.locfileid: "37547256"
---
# <a name="skype-room-system-manageability-and-tools"></a>Skype 室系統可管理性與工具
 
若要瞭解 Skype 室系統的管理工具，請閱讀本主題。
  
## <a name="administrative-portal"></a>管理入口網站

在商務用 Skype Server 內部部署中，您可以使用 Skype 室系統管理入口網站主動管理及監視貴組織內的 Skype 室系統部署。
  
如需詳細資訊，請參閱下列文章：
  
- [在商務用 Skype Server 中部署 SRS v1 管理網頁入口網站](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
  
## <a name="exchange-checklist"></a>Exchange 檢查清單

- 確認自動探索已設定，且可供 autodiscover.domain.com 的內部 DNS A/CNAME 記錄。
    
- Ping 自動探索（例如，Ping Autodiscover.contoso.com）。
    
- 使用 Microsoft Connectivity 分析程式工具測試自動探索服務。 選擇第一個測試，「我無法使用 Office Outlook 登入。」
    
- 如果會議室已有資源信箱，請將此帳戶延伸至 Skype 會議室系統（頁面底部的範例腳本）。
    
## <a name="skype-for-business-checklist"></a>商務用 Skype 檢查清單

- 執行下列工具：
    
  - 商務用 Skype 最佳做法分析工具     
  - 商務用 Skype 健康情況分析工具（Excel）    
  - 商務用 Skype 連線分析程式 32-位或64位
    
- 查看[適用于 Office 365 的實用的新疑難排解及分析工具](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/)。 確認您有商務用 Skype 文件庫和 Office Web Apps 伺服器，而且可以使用商務用 Skype 用戶端來共用 PowerPoint 投影片組。
    
- 如果會議室已有資源信箱，請針對商務用 Skype 啟用該信箱。
    
- 如有需要，請向 [會議室系統] 要求 [已執行] （電話號碼），並更新 Active Directory 工具中的 [一般電話] 欄位。
    
## <a name="network"></a>局域網

- 請確定您有 Skype 房間系統的有線網路連線。
    
- 閱讀商務用 Skype 的網路規劃指南。
    
- 從商務用 Skype 合作夥伴要求商務用 Skype 網路評量。
    
- 閱讀在商務用 Skype 健康情況分析工具（Excel）中捕獲的效能資料。
    
- 執行網路分析工具。
    
- 執行「預撥通話」工具。
    
## <a name="skype-room-system-security"></a>Skype 室系統安全性

Skype 室系統是內嵌的系統，可使用商務用 Skype 安全模型、版權管理和管理工具（例如 SCOM），在 Windows 部署中完整整合。 功能包括：
  
- [寫入篩選] 可防止磁片在使用者模式中寫入 
    
- [應用程式保險箱] 可防止未授權的 app 執行。 所有的 USB 埠在使用者模式中都停用。
    
  - 沒有任何標準 app 或檢視器位於 Skype 聊天室系統硬體上。 所有內容都是透過 HTTP 或 RDP 通訊協定來呈現。
    
  - 裝置電腦會執行 Windows Embedded Standard 7 作業系統。 所有硬體（包括裝置）都是由 OEM 合作夥伴提供。
    
  - 選用網域加入 Active Directory 網域服務（AD DS），啟用本機安全性帳戶管理和控制。
    
- 您也可以使用商務用 Skype 系統管理中心來管理本機管理員帳戶。
    
- Skype 室系統會透過標準的 Microsoft 更新程式來更新。
    
- Skype 室系統會與商務用 Skype 連線。
    
  - 商務用 Skype 使用端對端加密和授權進行所有通訊模式
    
  - Skype 室系統支援商務用 Skype 安全性與合規性標準。 如需詳細資訊，請參閱[商務用 Skype Server 中的安全性規劃](../../plan-your-deployment/security/security.md)。
    
## <a name="license"></a>授權

確認您使用 KMS 來啟用軟體。 如果是這樣，您可能需要檢查或新增商務用 Skype 用戶端 KMS 金鑰給它。 如果您使用的不是 KMS，請要求商務用 Skype 用戶端 MAK 的大量授權金鑰。
  
## <a name="license-keys"></a>授權金鑰

Skype 會議室系統會在背景中執行商務用 Skype 桌面用戶端。 如果 Skype 室系統是網域成員，就會發現您的 KMS。 （如果它有大量授權的 KMS 金鑰，就會自動啟動）。 大量授權也會提供 MAK，您可以在此輸入它顯示 xxxxx-xxxxx-xxxxx。 （您需要透過網際網路存取才能使用 MAK 啟用，但不是 KMS）。 如需詳細資訊，請參閱 Office 2013 的大量啟用。
  
- 若要進入 MAK 金鑰，請移至 OEM \>設定 SRS 授權工具。 按一下 [檢查狀態]。 當狀態顯示為「產品未啟用」時，請輸入金鑰。
    
- 如果在啟用期間收到錯誤訊息，指出「「軟體授權服務報告產品金鑰無效」，然後確認：
    
  - 已正確輸入金鑰。
    
  - 您輸入的是商務用 Skype MAK 金鑰，而不是其他金鑰。
    
  - 系統可存取網際網路。
    
- 您可以透過電話啟動，但必須先嘗試使用 SRS 授權工具啟動。 若要透過電話啟用，請啟動測試會議（不是太短的測試通話）。 在 Office 啟用嚮導中，選取 [電話啟用]、[撥打電話 Microsoft]、輸入該長數位，然後輸入回應。
    
## <a name="certificate-authority"></a>憑證授權單位

確認用來頒發 Office Web Apps Server 2013 憑證的憑證頒發機構有包含在憑證撤銷清單屬性中的 HTTP 路徑。
  
如果您使用商務用 Skype Server，請將證書檔案（.crt）匯入 Skype 房間系統。 它很容易從 CA 伺服器的 CertEnroll 共用，或在任何加入網域的電腦上的信任根資料夾中取得。
  
## <a name="certificates"></a>證書

確認您的認證機構有憑證撤銷清單的 HTTP 路徑。 如果不是，請更新您的 CA 以納入其中。
  
在 [系統設定\>憑證管理員] 下的 Skype 會議室系統管理員設定中安裝憑證。 您需要內部憑證的企業根 CA。
  
取得您所需憑證的其中一個方法是探索頒發您的憑證的 CA。 如果是商務用 Skype Server，請在商務用 Skype 中的電腦上\> ， \>按一下 [設定工具電話撥入會議設定]。 這會開啟由頒發內部憑證的 CA 保護的網頁。 按一下瀏覽器 [位址] 列上的 [鎖定] 圖示，以顯示安全性報告。 按一下 [查看憑證]，然後檢查 [CRL 發佈點] 屬性。 第二個 CN 參數應該是 CA 的伺服器名稱。 現在，針對該位址\\ \< CA 伺服器名稱\>\CertEnroll. 開啟 [Windows 資源管理器]。 將兩個 .crl 檔案和 .crt 檔案複製到快閃記憶體磁碟機，並將它放在智慧卡的左側。
  
將 .crt 檔案匯入 [受信任的聊天室憑證授權單位] 資料夾下的 Skype 房間系統。
  
將 .crl 檔案匯入到 [中間憑證頒發機構] 資料夾底下的 Skype 聊天室系統中。 （您必須將 [憑證管理員] 中的 [檔案延伸] 篩選器變更為 [crl]，才能查看檔案）。
  
注意： Office Web Apps 2013 server 可能會與商務用 Skype 共用同一個 CA。 如果不能在會議中共用 PowerPoint。 如上述所述，請查看並從 CA 網路共用 CertEnroll 中取得 CRT 和 CRL 檔案。 
  
網域成員資格可簡化部分作業，因為您可以將 Skype 房間系統視為 Windows 系統，而且它可以在 Active Directory 上尋找一些憑證的相關內容。 不過，最好是手動管理此專案。
  

