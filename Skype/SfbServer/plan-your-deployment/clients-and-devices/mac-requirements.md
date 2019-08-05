---
title: Mac 版商務用 Skype 用戶端需求
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 790d3e89-2b68-411b-b282-38de5d34dd10
description: 請閱讀本主題, 瞭解在 Mac 上執行商務用 Skype 的硬體、軟體及基礎結構需求。
ms.openlocfilehash: aca2329fa3e7d42dfd1aaf47e4c069773c7206f0
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/25/2019
ms.locfileid: "36193962"
---
# <a name="skype-for-business-on-mac-client-requirements"></a>Mac 版商務用 Skype 用戶端需求
 
請閱讀本主題, 瞭解在 Mac 上執行商務用 Skype 的硬體、軟體及基礎結構需求。
  
[Mac 版商務用 Skype 用戶端](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3#Mac)可供下載。
  
## <a name="hardware-and-software-requirements-for-skype-for-business-on-mac"></a>Mac 版商務用 Skype 的硬體和軟體需求

Mac 版商務用 Skype 用戶端需要 Mac OS X El Capitan 及更高版本, 且使用至少100MB 的磁碟空間。 我們支援所有內建的音訊和視頻裝置的使用。 外部裝置必須位於商務用[Skype 解決方案目錄](https://partnersolutions.skypeforbusiness.com/solutionscatalog)中。 
  
> [!NOTE]
> 此清單是初步的, 而且有些裝置可能會有資格使用 Lync, 但 Mac 版商務用 Skype 不支援此功能。 如需最低硬體需求, 請參閱[系統需求](https://products.office.com/en-us/office-system-requirements)。
  
### <a name="legacy-mac-clients"></a>舊版 Mac 用戶端

商務用 Skype Server 2015 也支援執行 Mac OS 10.5.8 的電腦上的下列舊版用戶端, 或最新的 service pack 或版本 (英特爾版) 作業系統 (目前不支援 Mac OS 10.9 作業系統)。 如需支援功能的詳細資訊, 請參閱[商務用 Skype 的桌面用戶端功能比較](desktop-feature-comparison.md)。
  
- Microsoft Lync for Mac 2011 (請參閱[Lync For mac 2011 部署指南](https://go.microsoft.com/fwlink/p/?LinkId=268786))
    
- Mac 版 Microsoft Communicator 2011 (請參閱[mac 版 communicator 2011 部署指南](https://go.microsoft.com/fwlink/p/?LinkId=268787))
 
商務用 Skype Server 2019 不支援這些用戶端。
   
## <a name="infrastructure-requirements-for-skype-for-business-on-mac"></a>Mac 版商務用 Skype 的基礎結構需求
<a name="Infrastructure"> </a>

Mac 版商務用 Skype 用戶端既能利用整合通訊管理平臺 (UCMP), 也能搭配我們行動用戶端使用的整合通訊 Web API (UCWA)。
  
用戶端與我們的行動用戶端有相同的需求, 那就是您必須擁有存取邊緣伺服器, 且部署的反向 Proxy 是受支援的配置。 
  
### <a name="authentication"></a>Authentication

Mac 版商務用 Skype 用戶端支援以 Cert 為基礎的驗證、Microsoft 新式驗證, 以及在部署及啟用時進行多重要素驗證。
  
> [!NOTE]
> 由於目前的限制, 使用者的 Exchange 認證必須是其商務用 Skype 認證。 
  
### <a name="certificates"></a>證書

在存取邊緣使用的憑證, 反向 Proxy 與前端伺服器不能使用 SHA-512 雜湊演算法。
  
HTTP 憑證吊銷清單必須由用戶端定義並存取。 例如, 我們不支援憑證中的 LDAP 專案作為您的憑證吊銷清單。
  
### <a name="dns"></a>DN

行動必須正確部署, 才能讓 Mac 用戶端上的商務用 Skype 正常運作。 常見的失敗案例是在內部網路上同時解析下列兩個 DNS 專案:
  
- lyncdiscoverinternal.\<sipdomain\>
    
- lyncdiscover.\<sipdomain\>
    
如需詳細資訊, 請參閱:[在 Lync server 2013 中部署行動](https://go.microsoft.com/fwlink/p/?LinkId=798224), 以及[Microsoft Lync Server 2010 行動指南](https://go.microsoft.com/fwlink//p/?LinkId=798226)。
  
## <a name="see-also"></a>另請參閱
<a name="Infrastructure"> </a>

[商務用 Skype Server 的 DNS 需求](../../plan-your-deployment/network-requirements/dns.md)

[常見問題](https://go.microsoft.com/fwlink/p/?LinkId=798227)
  
[已知問題](https://go.microsoft.com/fwlink/p/?LinkId=798228)
