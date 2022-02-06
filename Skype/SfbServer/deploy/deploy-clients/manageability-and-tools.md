---
title: Skype 會議室系統管理性與工具
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: 閱讀此主題以瞭解 Skype 會議室系統的管理工具。
---

# <a name="skype-room-system-manageability-and-tools"></a>Skype 會議室系統管理性與工具
 
閱讀此主題以瞭解 Skype 會議室系統的管理工具。
  
## <a name="administrative-portal"></a>管理入口網站

針對商務用 Skype Server 的內部部署，您可以使用 Skype 會議室系統管理入口網站，主動管理及監視組織內 Skype 的室內系統部署。
  
如需詳細資訊，請參閱下列文章：
  
- [在商務用 Skype Server 中部署 SRS v1 管理網頁入口網站](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
  
## <a name="exchange-checklist"></a>Exchange 檢查清單

- 確認自動探索已設定，且內部 DNS A/CNAME 記錄可用於 autodiscover.domain.com。
    
- Ping 自動探索 (例如，Ping Autodiscover.contoso.com) 。
    
- 使用 Microsoft Connectivity Analyzer 工具測試自動探索服務。 選擇 [我無法使用 Office Outlook 登入] 第一個測試。
    
- 如果會議室已有資源信箱，請在) 頁面底部的 [Skype 會議室系統] (範例腳本中，擴充此帳戶。
    
## <a name="skype-for-business-checklist"></a>商務用 Skype 檢查清單

- 執行下列工具：
    
  - 最佳做法分析程式商務用 Skype     
  - 商務用 Skype 狀況分析工具 (Excel)     
  - 商務用 Skype Connectivity Analyzer 32 位或64位
    
- 回顧[Office 365 的有用的新疑難排解和分析工具](/archive/blogs/educloud/useful-new-troubleshooting-and-analysis-tools-for-office-365)。 確認您有商務用 Skype 集區和 Office 網頁應用程式伺服器，而且可以使用商務用 Skype 用戶端共用 PowerPoint 的圖案。
    
- 如果會議室已有資源信箱，請為商務用 Skype 啟用該信箱。
    
- 如有需要，針對會議室系統要求 (電話號碼) ，並更新 Active Directory 工具中的 [一般電話] 欄位。
    
## <a name="network"></a>網路

- 確定您有 Skype 房間系統的有線網路連接。
    
- 閱讀商務用 Skype 的網路規劃指南。
    
- 從商務用 Skype 合作夥伴要求商務用 Skype 網路評估。
    
- 讀取商務用 Skype 狀況分析工具 (Excel) 中所捕獲的效能資料。
    
- 執行網路分析工具。
    
- 執行「呼叫前診斷」工具。
    
## <a name="skype-room-system-security"></a>Skype 房間系統安全性

Skype 會議室系統是內嵌系統，可以使用商務用 Skype 安全性模型、版權管理和管理工具（例如 SCOM），充分整合在 Windows 部署中。 功能包括：
  
- 寫入篩選器，以在使用者模式中防止磁片寫入 
    
- 應用程式鎖定者，以防止未授權的應用程式執行。 所有的 USB 埠都會在使用者模式中停用。
    
  - 沒有標準應用程式或檢視器位於 Skype 房間系統硬體上。 所有內容都透過 HTTP 或 RDP 通訊協定來呈現。
    
  - 裝置電腦會執行 Windows 內嵌標準7作業系統。 所有的硬體（包括裝置）都是由 OEM 合作夥伴提供。
    
  - 選用網域加入 Active Directory 網域服務 (AD DS) ，啟用本機安全性帳戶管理與控制。
    
- 您也可以使用商務用 Skype 系統管理中心來管理本機系統管理員帳戶。
    
- Skype 房間系統會透過標準的 Microsoft 更新程式進行更新。
    
- Skype 房間系統會與商務用 Skype 連接。
    
  - 商務用 Skype 針對所有通訊模式使用端對端加密和授權
    
  - Skype 會議室系統支援商務用 Skype 安全性和合規性標準。 如需詳細資訊，請參閱[Plan for security in Business Server Skype for security](../../plan-your-deployment/security/security.md) 。
    
## <a name="license"></a>License

請確認您使用 KMS 來啟用軟體。 如果是的話，您可能需要檢查或新增商務用 Skype 用戶端 KMS 金鑰。 如果您未使用 KMS，請針對商務用 Skype 用戶端 MAK 要求大量授權金鑰。
  
## <a name="license-keys"></a>授權金鑰

Skype 會議室系統會在背景中執行商務用 Skype 桌面用戶端。 如果 Skype 的會議室系統是網域成員，則會發現您的 KMS。  (，而且如果有大量授權 KMS 金鑰將會自動啟用) 。 大量授權也會提供 MAK，當您輸入時，它會顯示 xxxxx xxxxx。  (您必須使用 MAK 來啟用 Internet 存取，但不是 KMS) 。 如需詳細資訊，請參閱大量啟用 Office 2013。
  
- 若要輸入 MAK 金鑰，請移至 OEM 設定 \> SRS 授權工具。 按一下 [檢查狀態]。 當狀態為 "product 未啟用" 時，輸入機碼。
    
- 在啟用時，您會收到錯誤 [軟體授權服務報告產品金鑰無效]，然後確認：
    
  - 已正確輸入機碼。
    
  - 您輸入的是商務用 Skype MAK 金鑰，而不是另一個金鑰。
    
  - 系統可存取網際網路。
    
- 您可以透過電話啟動，但必須先嘗試使用 SRS 授權工具啟用。 若要透過電話啟動，請啟動測試會議 (非短) 的測試呼叫。 在 [Office 啟用] 嚮導中，選取 [電話啟用]，撥打 Microsoft，輸入長號碼，然後輸入回應。
    
## <a name="certificate-authority"></a>憑證授權單位單位

確認用來發出 Office Web Apps Server 2013 憑證的憑證授權單位單位有 HTTP 路徑包含在 [憑證吊銷清單] 屬性中。
  
將憑證檔案 ( .crt) 匯入 Skype 的房間系統（如果使用商務用 Skype Server）。 它很容易從 CA 伺服器的 CertEnroll 共用，或任何已加入網域之電腦的受信任根資料夾中取得。
  
## <a name="certificates"></a>憑證

確認您的憑證授權單位有憑證吊銷清單的 HTTP 路徑。 如果不是，請更新您的 CA 以包含其中一個。
  
在 [系統設定 \> 憑證管理員] 底下的 Skype 房間系統管理員安裝中，安裝憑證。 您必須是內部憑證的 Enterprise 根 CA。
  
取得您所需憑證的一種方法是探索發行憑證的 CA。 商務用 Skype Server，請在商務用 Skype 上的電腦上，按一下 [設定 \> 工具 \> 撥入式會議設定]。 這會開啟由簽發內部憑證之 CA 所保護的網頁。 按一下瀏覽器位址列上的鎖定圖示，以顯示安全性報告。 按一下 [查看憑證]，然後檢查 [CRL 發佈點] 屬性。 第二個 CN 參數應為 CA 的伺服器名稱。 現在，針對該位址 \\ \< CA Server Name \> \CertEnroll. 開啟 Windows Explorer 將兩個 .crl 檔和 .crt 檔複製到快閃記憶體磁碟機，並將它放在智慧卡的左側。
  
將 .crt 檔案匯入「受信任的會議室憑證授權單位」資料夾底下的 Skype 房間系統。
  
在 [中級憑證授權] 資料夾底下的 Skype 房間系統上，匯入 .crl 檔案。  (您必須將憑證管理員中的副檔名篩選器變更為 crl，以查看檔案) 。
  
附注： Office Web Apps 2013 server 可能與商務用 Skype 共用相同的 CA。 如果不能在會議中共用 PowerPoint。 如以上所述，請與其一起檢查，並從 CA 網路共用 CertEnroll 取得 CRT 和 CRL 檔案。 
  
網域成員資格可以簡化某些事項，因為您可以將 Skype 的會議室系統視為 Windows 系統，而且可以針對某些憑證方面使用 Active Directory。 不過，最好是手動管理這種方式。
