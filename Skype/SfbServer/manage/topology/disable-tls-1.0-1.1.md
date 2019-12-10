---
title: 在商務用 Skype Server 2015 中停用 TLS 1.0/1。1
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 摘要：在您的環境中，準備及執行停用 TLS 1.0 和1.1。
ms.openlocfilehash: f6fa608174bc22bc91512a69cc67a688b9bc7bb9
ms.sourcegitcommit: 0dba0ad1f8f00415c6437cadabed0548ce3281b1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/10/2019
ms.locfileid: "39919307"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a>在商務用 Skype Server 2015 中停用 TLS 1.0/1。1

本文的目的是為您提供在您的環境中準備及實現停用 TLS 1.0 和1.1 所需的必要指導方針。 這個程式需要大量的規劃及準備。 在您針對貴組織停用 TLS 1.0 和1.1 時，請仔細閱讀本文中的所有資訊。 請注意，有許多外部相依性與連接條件可能會因為停用 TLS 1.0/1.1 而受到影響，所以需要進行大量的規劃與測試。

## <a name="in-this-article"></a>本文內容

- [背景與範圍](#background)
- [先決條件與處理常式](#prerequisites-and-process)
- [高級部署案例](#advanced-deployment-scenarios)

## <a name="background"></a>背景

提供 TLS 1.0 和1.1 的主要驅動程式：停用商務用 Skype Server 內部部署支援是支付卡行業（PCI）安全標準委員會與聯邦資訊處理標準需求。 您可以[在此](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls)找到更多關於 PCI 需求的資訊。  Microsoft 無法提供您的組織是否需要遵守這些或其他需求的指導方針。 您必須判斷您是否需要在您的環境中停用 TLS 1.0 和/或1.1。

Microsoft 在[此處](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)提供 TLS 的白皮書，我們也建議您在此[Exchange 博客](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)中提供背景閱讀。

## <a name="supportability-scope"></a>支援範圍

*範圍*指的是支援界限。 *經過充分測試和支援*的意思是，我們完全支援並針對所列出的產品版本，對 TLS 1.0 和1.1 停用。 *目前正在調查*的意思是，我們正在積極調查如何將這些產品帶入 TLS 停用支援的範圍。 [不在*範圍*] 表示這些產品版本不支援停用 TLS 1.0 或1.1，且無法運作，但已注明例外狀況。

### <a name="fully-tested-and-supported-servers"></a>經過充分測試和支援的伺服器

- 商務用 Skype Server 2019 CU1 17.0.2046.123 （2019年6月）或更高版本
- 商務用 Skype Server 2015 CU9 6.0.9319.548 （5月2019）或更高版本的 Windows Server 2012 （含 KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in)或取代更新）、2012 R2 或2016。
- 在 Windows Server 2008 R2、2012（含 KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in)或取代更新）或 2012 r2 的就地升級商務用 Skype Server 2015，具有 CU9 6.0.9319.548 （可能2019）或更高版本。
- Exchange 連線與 Outlook Web App 與 Exchange Server 2010 SP3 RU19 或更新版本，請參閱[這裡](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)的指導方針
- Survivable 分支裝置（SBA）與商務用 Skype Server 2015 CU6 HF2 或更新版本（向您的供應商確認他們已封裝 appropiate 更新，且已提供給您的裝置）
- Survivable 分支伺服器（SBS）與商務用 Skype Server 2015 CU6 HF2 或更新版本
- Lync Server 2013 **Edge 角色**，這是因為 edge 角色在 Windows Fabric 1.0 上沒有相依性。

### <a name="fully-tested-and-supported-clients"></a>經過完全測試且支援的用戶端

- Lync 2013 （商務用 Skype）桌面用戶端、MSI 及 C2R，包括基本[15.0.5023.1000 或更新版本](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)
- 商務用 Skype 2016 桌面用戶端、MSI [16.0.4678.1000 或更新版本](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323)，包括基本
- 商務用 Skype 2016 按一下以執行需要[2018 年4月](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus)的更新： 
    - 每月與半年目標，16\.0\.9126\.2152 或更新版本
    - 半年和延遲頻道、16\.0\.8431\.2242 或更高版本
- Mac 版商務用 Skype 16.15 或更新版本
- IOS 版和 Android 版商務用 Skype 6.19 或更新版本
- Microsoft 球隊聊天室（先前稱為 Skype 會議室 System V2 SRS V2）4.0.64.0 （2018年12月）或更高版本
- 根據 KB4499162 （可能是2019、OS 組建15063.1835）或更高版本的小組版 Surface Hub 更新
- Skype Web App 2015 CU6 HF2 或更新版本（隨附于伺服器）

### <a name="currently-being-investigated"></a>目前正在調查

- 通話品質儀表板（在 TLS 1.0 之後的新安裝，1.1 已停用，請參閱下列） *
 
### <a name="out-of-scope"></a>超出範圍

除非另有說明，否則下列產品不在 TLS 1.0/1.1 停用支援的範圍內，且在已停用 TLS 1.0 和1.1 的環境中將無法運作。 意義如下：如果您仍然使用範圍外的伺服器或用戶端，則您必須在商務用 Skype Server 內部部署中的任何地方停用 TLS 1.0/1.1，才能進行更新或移除。

- Lync Server 2013
- Lync Server 2010
- Windows Server 2008 或更低版本
- Lync for Mac 2011
- 適用于行動裝置的 Lync 2013-iOS、iPad、Android 或 Windows Phone
- Lync "MX" Windows Store 用戶端
- Lync 會議室系統（a.k.a。 SRSv1). LRS 已達到2018年10月9日的支援終止，且不會更新以支援 TLS 1.2。
- 所有 Lync 2010 用戶端
- Lync 手機版-[這裡](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035)是更新的指導方針。
- 2013基礎 Survivable 分支裝置（SBA）或 Survivable 分支伺服器（SBS）
- 雲端連接器版本（CCE）
- Windows Phone 版商務用 Skype

### <a name="exceptions"></a>例外狀況

#### <a name="lync-server-2013"></a>Lync Server 2013

Lync Server 2013 會在 Windows Fabric 版本1.0 上相依相依性。  在 Lync Server 2013 的設計階段，為其引人注目的新分散式架構選擇了 Windows Fabric 1.0，以提供複製、高可用性和容錯能力。  隨著時間的推移，在後續版本中，商務用 Skype Server 和 Windows Fabric 都已大大改善這種聯合架構，並明顯重新設計。  目前的商務用 Skype 2015 伺服器使用 Windows Fabric 3.0，例如。

遺憾的是，Windows Fabric 1.0 不**支援 TLS 1.2。 不過，我們會更新 Lync Server 2013，以搭配 TLS 1.2 使用**。 這將會放在 Lync Server 2013 的下一個累積更新中。  我們提供 TLS 1.2 支援，以啟用共存、遷移、同盟及混合式案例。

如果您的組織必須停用 TLS 1.0 和1.1，且您目前使用的是 Lync Server 2013，我們建議您開始進行規劃，您可能必須就地升級或並排遷移（新的池、移動使用者）至 SkypeBusiness Server 2015 或更新版本。  或者，您可能想要加速遷移到商務用 Skype Online。

#### <a name="call-quality-dashboard"></a>通話品質儀表板

內部部署通話品質儀表板目前在新安裝期間（第一次安裝到內部部署環境中），在 TLS 1.0 上有相依性。  我們目前正在調查此問題，並計畫在不久的將來發佈修正程式。  如果您打算安裝 CQD 並停用 TLS 1.0，我們建議您先完成 CQD 安裝，然後再繼續進行 TLS 1.0 停用。

#### <a name="third-party-devices"></a>協力廠商裝置

在協力廠商裝置上（例如3PIP 手機、視訊會議、反向代理及負載平衡器），請務必驗證 TLS 1.2 支援、小心地進行測試，並視需要與廠商聯繫。

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a>在邊緣伺服器上停用 TLS 1.0/1.1 時的同盟考慮

您必須仔細規劃並考慮在 Edge 伺服器上停用 TLS 1.0/1.1 的影響。  一旦 TLS 1.0 和1.1 停用之後，您可能會發現其他組織無法再與您的組織聯盟。

您可以選擇將 TLS 1.0/1.1 保留在 Edge 伺服器上，以維持與未修補（SfB 2015、Lync 2013）或舊版（2010）外部系統的向後相容性。

如果您的邊緣網路（或任何網路）都屬於 PCI 標準，Microsoft 將無法提供相關的建議或建議。必須由個別公司決定。

商務用 Skype Online 目前支援 TLS 1.2，所以不會對線上的混合式/同盟產生任何影響。

PIC （公用 IM 連線）至 Skype 消費者服務：我們不想停用 TLS 1.0/1.1 來影響[Skype 連通性](../../deploy/deploy-skype-connectivity.md);Microsoft PIC 閘道已有支援 TLS 1.2 的功能。

## <a name="prerequisites-and-process"></a>先決條件與處理常式

除了上述所述位置之外，只要 TLS 1.0 和1.1 停用超出範圍的伺服器，用戶端和裝置就能正常運作，或者完全不需要。 這可能表示您需要暫停並等待 Microsoft 的更新指導方針。 當您認為符合所有需求，並想要解決差距時，請繼續進行。

從較高層面來看，在商務用 skype server 2019 已準備好進行安裝時，商務用 Skype Server 2015 將會要求您安裝 CU9、將預先必備的更新套用至 .NET 與 SQL、部署必備項登錄機碼，以及最後一個獨立的一輪的 OS 設定更新（亦即，透過登錄檔案匯入停用 TLS 1.0 和1.1）。 在您的環境中，在任何伺服器上停用 TLS 1.0 和1.1 之前，請務必先完成所有先決條件（包括商務用 Skype Server 2015 CU6 HF2）的安裝。 每個商務用 Skype 伺服器，包括 Edge 角色和 SQL Backends，都需要更新。 另外，請確定所有支援的（範圍內）用戶端都已更新為所需的最低版本。 別忘了更新管理工作站。

我們想要遵循在升級商務用 Skype 伺服器的一般運算順序。 以您正常的方式來對待控制器池、持續聊天和配對的池。 升級的[順序與](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)[方法如下所述。](topology.md)

### <a name="high-level-process"></a>高層次處理常式

1. 在設定生產伺服器之前，請先測試實驗室中的所有步驟。
2. 在每個要更新的個別伺服器上，備份並保留一份匯出的登錄複本。 您無法在伺服器之間共用註冊表;它們包含唯一的電腦機密鑰。
3. 將所有商務用 Skype 2015 伺服器升級為 CU9 或更新版本。 如果是商務用 Skype Server 2019，請升級至 CU1 或更新版本。
4. 安裝所有伺服器的所有先決條件。
5. 部署必備的登錄機碼。
6. 確定所有的範圍內用戶端都已更新。
7. 透過登錄匯入來停用 TLS 1.0 和1.1。
8. 驗證工作負載是否如預期運作。
    - 如果遇到問題，請先進行疑難排解並解決，或
    - 從步驟2還原註冊表，以重新啟用 TLS 1.0 和1。1
9. 確認只使用 TLS 1.2。

### <a name="install-prerequisites-to-all-servers"></a>安裝系統必備元件至所有伺服器

在您開始在商務用 Skype Server 2015 部署的作業系統層級停用 TLS 1.0 和1.1 之前，需要進行廣泛的相依性更新。 下列是可支援 TLS 1.2 的最低版本。 在您開始停用 TLS 1.0 和1.1 之前，請先在您的環境中的每一個商務用 Skype 伺服器上部署所有必備更新。

- 商務用 Skype Server 2015 CU9 6.0.9319.548 （可能2019）或更高版本
- 在 registry 中啟用 SchUseStrongCrypto 的[.Net Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167)或更新版本（如下所述）
- 在所有商務用 Skype 2015 伺服器和 backends，必須更新 SQL。 首先更新企業版池 SQL Backends，然後再更新其各自的 FEs。 
    - [SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926)或更高版本/sql SERVER 2012 SP2 + CU16 或更新版本/sql SERVER [2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014)或更高版本/sql server 2014 sp2
     - [Sql server Native Client for SQL Server 2012](https://www.microsoft.com/download/details.aspx?id=50402)
     - [MICROSOFT ODBC Driver 11 FOR SQL Server](https://www.microsoft.com/download/details.aspx?id=36434)或更新版本
     - [SQL Server 2014 SP2 的共用管理物件](https://www.microsoft.com/download/details.aspx?id=53164)
     - [SQL server 2014 SP2 的 SQLSysClrTypes](https://www.microsoft.com/download/details.aspx?id=42295)

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a>安裝必備元件（建議作業順序）的基本步驟

1. 安裝商務用 Skype Server CU9 更新至所有伺服器。 
    1. 使用更新程式安裝元件的更新程式。
    2. 根據已記錄的程式更新資料庫。 如果是商務用 Skype Server 2015，請參閱 KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)。
    3. 在進行任何其他變更前，先驗證部署中的產品功能。
2. 下載 .NET 4.7 離線安裝程式。 
    1. Reference[https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)
    2. 確定商務用 Skype Server 2015 服務已在前端伺服器上停止。
    3. Reference[https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)
    4. Ex （標準版）：```Stop-CsWindowsService```
    5. Ex （企業版）：```Invoke-CsComputerFailover```
    6. 執行安裝程式套件。
    7. 重新開機伺服器。
3. 在所有伺服器上更新 SQL Express 2014。 
    1. Reference[https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)
    2. 下載 SQL 2014 SP2 
        - Reference[https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)
    3. 將安裝媒體複製到伺服器上的資料夾（例如： C：\ 01_2014SqlSp2）
    4. 確保前端伺服器上的商務用 Skype Server 2015 服務已停止 
        - Ex （標準版）：```Stop-CsWindowsService```
        - Ex （企業版）：```Invoke-CsComputerFailover```
    5. 開啟管理員命令提示字元，並升級所有已安裝的元件和實例 
        - 範例： C：\ 01_2014SqlSp2 \SQLServer2014SP2-KB3171021-x64-ENU.exe/qs/IAcceptSQLServerLicenseTerms/Action = Patch/AllInstances
4. 更新 SQL 原生用戶端。 
    1. 參照： [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)。
    2. 下載自[https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)
    3. 確保前端伺服器上的商務用 Skype Server 2015 服務已停止。 
        - Ex （標準版）：```Stop-CsWindowsServices```
        - Ex （企業版）：```Invoke-CsComputerFailover```
    4. 停止執行已安裝的 SQL 實例 
        - 例如```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```
        - 例如```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```
        - Ex （僅適用于標準版）：```Get-Service 'MSSQL$RTC' | Stop-Service```
    5. 安裝更新。
5. 更新 ODBC Driver 11 for SQL Server，以包括 TLS 1.2 （KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)）的支援。
    1. 下載[SQL Server 的 ODBC Driver 11 （Windows 版）](https://www.microsoft.com/download/confirmation.aspx?id=36434)。
    2. 確定商務用 Skype Server 2015 服務已在前端伺服器上停止。
        - 範例（標準版）：```Stop-CsWindowsService```
        - 範例（企業版）：```Invoke-CsComputerFailover```
    3. 安裝更新。
6. 部署必備的登錄機碼。

### <a name="pre-requisite-registry-keys"></a>預先必備的登錄機碼

將下列測試複製/貼上到記事本中，並重新命名 TLSPreReq 或您選擇的名稱，然後匯入：

```
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v2.0.50727]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v4.0.30319]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v2.0.50727]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp]

"DefaultSecureProtocols"=dword:00000AA0

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp]

"DefaultSecureProtocols"=dword:00000AA0

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Client]

"DisabledByDefault"=dword:00000000

"Enabled"=dword:00000001

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Server]

"DisabledByDefault"=dword:00000000

"Enabled"=dword:00000001
```

針對企業版池的 SQL back end，必須將先決條件與 TLS 停用視為任何 SQL 或 OS 更新;請參閱：[https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)

雖然必備的應用程式和 TLS 停用步驟都可以結合，但我們強烈建議先套用所有先決條件，然後再繼續停用作業系統層級的 TLS 1.0 和1.1。 最佳做法做法是部署所有先決條件、確認工作負荷全部正常運作並如期進行，然後再繼續進行 TLS 1.0/1.1 的準備。

### <a name="disable-tls-10-and-11-via-registry-import"></a>透過登錄匯入來停用 TLS 1.0 和1。1

在您繼續進行後續步驟之前，*請確定您已完成所有先決條件及更新的商務用 Skype 伺服器*。

將下列文字複製到記事本檔案中，然後將它重新命名為**TLSDisable**：

```
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Cryptography\Configuration\SSL\00010002]

"Functions"="TLS_ECDHE_ECDSA_WITH_AES_256_GCM_SHA384_P384,TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256_P256,TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384_P384,TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256_P256,TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA384_P384,TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA256_P256,TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384_P384,TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256_P256,TLS_RSA_WITH_AES_256_GCM_SHA384,TLS_RSA_WITH_AES_128_GCM_SHA256,TLS_RSA_WITH_AES_256_CBC_SHA256,TLS_RSA_WITH_AES_128_CBC_SHA256"

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL]

"AllowInsecureRenegoClients"=dword:00000000

"AllowInsecureRenegoServers"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\AES 128/128]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\AES 256/256]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\DES 56/56]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\NULL]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 128/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 40/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 56/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 56/56]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 128/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 40/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 56/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 64/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\Triple DES 168]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\MD5]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA256]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA384]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA512]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\Diffie-Hellman]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\ECDH]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\PKCS]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000
```

在您想要停用 TLS 1.0 和1.1 的每個伺服器上匯入 .reg 檔案。 重新開機伺服器。 一旦服務回到線上，就移至下一個伺服器。 企業版池的方法與任何作業系統更新所需的方式相同。

您可能已經注意到，我們執行的動作不只是在這裡停用 TLS 1.0 和1.1。 我們支援密碼套件重新排序（如上所示）及停用一些較舊的弱密碼。 這是我們第一次在商務用 Skype Server 上對 SCHANNEL 和加密 API 所做的這些變更，請務必注意，這些變更是我們目前所支援的，且目前已測試過。 我們可能會在未來考慮其他設定，但目前請不要在您的實現中修改登錄匯入檔案。

### <a name="validate-that-workloads-are-functioning-as-expected"></a>驗證工作負載是否如預期運作

在您的環境中停用 TLS 1.0 和1.1 後，請確定您的所有主要工作負載都如期運作，例如 IM & 目前狀態、P2P 通話、企業語音等。

**僅驗證正在使用的 TLS 1。2**

讓您的安全小組執行新的商務用 Skype 通訊審計，以確保較舊的通訊協定 TLS 1.0 和1.1 已不再使用。

或者，您也可以使用 Internet Explorer，在已停用 TLS 1.0 和 TLS 1.1 之後，從商務用 Skype Server 2015 測試 TLS 連線至 web 服務。

1. 啟動 Internet Explorer。
2. 選取 [**工具** > **網際網路選項**]。
3. 選取 [**高級**] 索引標籤。
4. 在 [**設定**] 底下，向下滾動至底部。
5. 確認 TLS 1.0、TLS 1.1 及 TLS 1.2 已啟用。
6. 流覽您 SfB 2015 池的內部 Web 服務 URL （應該能成功連接）。
7. 回到 Internet Explorer 並停**用只使用 TLS 1.2**的選項。
8. 再次流覽您 SfB 2015 池的內部 Web 服務 URL （應該無法連線）。

![網際網路選項](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a>高級部署案例

因為在商務用 Skype Ser 2015 中需要一些相依性先決條件來支援 TLS 1.2，所以在已停用 TLS 1.0 和1.1 的任何系統上，從 RTM 媒體進行安裝將會失敗。

**在您的環境中停用 TLS 1.0 和1.1 後，部署新的標準版伺服器或企業版池。**

**選項1：** 使用[SmartSetup](../../deploy/install/install-skype-for-business-server.md)。 請注意，我們正在更新 SmartSetup，以在未來的 CU 中容納更新的 SQL 二進位檔案，並將于未來更新此文章。

**選項2：** 預先安裝本機 SQL 實例（RTCLOCAL 和 LYNCLOCAL）

1. 將 SQL Express 2014 SP2 （SQLEXPR_x64 .exe）下載並複製到 FE 上的本機資料夾。 假設 [資料夾路徑] <SQL_FOLDER_PATH>。
2. 啟動 PowerShell 或命令提示字元，然後流覽至 <SQL_FOLDER_PATH>。
3. 若要建立 RTCLOCAL SQL 實例，請執行下列命令。 請等到 SQLEXPR_x64 完成，然後再繼續：

    SQLEXPR_x64 .exe/Q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE/ACTION = 安裝/FEATURES = SQLEngine，工具/INSTANCENAME = RTCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin\Administrators"/BROWSERSVCSTARTUPTYPE = "Automatic"/AGTSVCACCOUNT = "NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = Automati
1. 若要建立 LYNCLOCAL SQL 實例，請執行下列命令。 等到 SQLEXPR_x64 完成之後，再繼續進行下一個步驟：

    SQLEXPR_x64 .exe/Q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE/ACTION = 安裝/FEATURES = SQLEngine，工具/INSTANCENAME = LYNCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin\Administrators"/BROWSERSVCSTARTUPTYPE = "Automatic"/AGTSVCACCOUNT = "NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = 自動
1. 執行商務用 Skype Server 2015 RTM 設定。
2. 請依照上述 [先決條件] 區段的其餘步驟進行。

**選項3：** 您也可以在本機安裝媒體目錄中手動取代二進位檔案，如下所示：

1. [安裝商務用 Skype Server 的先決條件](../../deploy/install/install-prerequisites.md)  
2. 安裝 .NET 4.7： 
      - **注意：** 我們最先在商務用 Skype Server 2015 CU5 （6.0.9319.281）中推出 .NET 4.7 支援。 因此，在後續步驟中，我們會在主要安裝之前更新核心元件。
      - 下載： https://www.microsoft.com/download/details.aspx?id=55167。 
      - 參考：[應該在商務用 Skype Server 2015 部署之前安裝的軟體](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)
3. 複製 ISO 檔案/資料夾： 
    - 在已附加商務用 Skype Server 2015 ISO 的情況下，開啟附加的磁片磁碟機根目錄（例如，在檔案資源管理\)器中則是： D：）。
    - 將所有資料夾和檔案複製到本機磁片上的資料夾（例如： C:\SkypeForBusiness2015ISO）。
    - **注意：** 在安裝元件之前，必須更新部分檔案，以支援 TLS 1.2。
4. 取代 MSI/EXE 套件： 
    - 在本機電腦上的安裝媒體的/Setup/amd64/資料夾中，取代現有的 MSI 和 EXE 套件。
    - SQL 2014 SP2 Express：https://www.microsoft.com/en-us/download/details.aspx?id=53167 
        - 在本機電腦上重新命名為 SQLEXPR_x64，並取代安裝媒體的 Setup/amd64/資料夾中現有的檔案。
    - SQL 原生用戶端：https://www.microsoft.com/en-us/download/details.aspx?id=50402 
        - **注意：** 如有需要，請重新命名此 sqlncli，然後取代安裝媒體的 Setup/amd64/資料夾中存在的現有檔案。
    - SQL 管理物件：https://www.microsoft.com/en-us/download/details.aspx?id=53164 
        - **注意：** 功能套件將會有大量的專案可供下載。 選取即可下載 SharedManagementObjects。
        - **注意：** 取代安裝媒體的 Setup/amd64/資料夾中存在的現有檔案。
    - SQL CLR 類型：https://www.microsoft.com/en-us/download/details.aspx?id=53164 
        - **注意：** 功能套件將會有大量的專案可供下載。 選取以下載 CQLSysClrTypes （僅限 msi）
        - **注意**：取代安裝媒體的 Setup/amd64/資料夾中存在的現有檔案。
5. 安裝核心元件： 
    - 從安裝媒體的 Setup/amd64/資料夾執行 setup.exe。 依照指示安裝核心元件
    - 關閉核心元件。
6. 更新核心元件： 
    - 下載商務用 Skype 更新安裝程式。
    - 執行安裝程式以更新核心元件並安裝效能計數器。
    - **注意：** CU6HF2 發行時，「自動更新」功能目前只會安裝到 CU6。 因此，必須單獨執行更新程式，才能將核心元件更新為6.0.9319.516。
    - Referencehttps://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015
7. 安裝系統管理工具（選用）： 
    - 這將會安裝 Microsoft SQL Server 2012 原生用戶端、SQL Server 2014 管理物件（x64），以及 SQL Server 2014 （x64）的 Microsoft System CLR 類型（使用已更新的檔案）。 此外，您也可以在本機電腦上使用商務用 Skype Server 2015 拓撲建立器和 [控制台]。
8. 安裝本機配置存放區（步驟1）： 
     - 開啟 [部署嚮導]，按一下 [安裝或更新商務用 Skype Server System]，然後按一下 [**執行**] （在步驟1：安裝本機配置存儲區）。
     - 按一下 [**安裝本機設定存儲**] 對話方塊中的 **[下一步**]。
     ![[安裝本機設定儲存] 對話方塊](../../media/local-configuration-store.png)
     - 查看結果，並確定任務狀態為 [已完成]。 按一下 [**查看記錄**]，查看產生的記錄檔。
     ![任務狀態顯示為已完成](../../media/local-configuration-task-completed.png)
     - 按一下 **[完成]**。
9. 設定或移除商務用 Skype Server 元件（步驟2）：
    - 開啟 [部署] 嚮導，按一下 [**安裝或更新商務用 Skype Server System**]，然後按一下 [**執行**] 步驟2：設定或移除商務用 skype server 元件
    - 按一下 [設定商務用 Skype Server 元件] 對話方塊中的 **[下一步**]。
    ![[設定商務用 Skype Server 元件] 視窗](../../media/set-up-skype-for-business-server-components-window.png)
    - 使用 [查看記錄] 查看記錄，並驗證安裝程式是否已完成且沒有任何問題。 
    - 按一下 **[完成]**。
10. 根據需要繼續進行其他安裝和設定（您可以隨時繼續執行正常安裝程式）。
