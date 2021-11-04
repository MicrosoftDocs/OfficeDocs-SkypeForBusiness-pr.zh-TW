---
title: 商務用 Skype Mac 用戶端需求
ms.author: v-mahoffman
author: cichur
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 790d3e89-2b68-411b-b282-38de5d34dd10
description: 閱讀此主題以瞭解在 Mac 上執行商務用 Skype 的硬體、軟體和基礎結構需求。
ms.openlocfilehash: 3a4d80bea5bd56f94b5239a537d059c4409d8f33
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60745909"
---
# <a name="skype-for-business-on-mac-client-requirements"></a>商務用 Skype Mac 用戶端需求
 
閱讀此主題以瞭解在 Mac 上執行商務用 Skype 的硬體、軟體和基礎結構需求。
  
[Mac 用戶端上的商務用 Skype](https://products.office.com/skype-for-business/download-app?tab=tabs-3#Mac)可供下載。
  
## <a name="hardware-and-software-requirements-for-skype-for-business-on-mac"></a>Mac 版商務用 Skype 的硬體和軟體需求

mac 用戶端上的商務用 Skype 需要 mac OS X El Capitan 及更高版本，且至少使用磁碟空間100MB。 我們支援使用內建的音訊及視頻裝置。 外部裝置必須列在[Microsoft Teams 裝置](https://www.microsoft.com/microsoft-teams/across-devices/devices)上。 
  
> [!NOTE]
> 這個清單是初步的，有些裝置可能符合 Lync，但不支援 Mac 上的商務用 Skype。 如需最低硬體需求，請參閱 [系統需求](https://products.office.com/office-system-requirements) 。
  
### <a name="legacy-mac-clients"></a>舊版 Mac 用戶端

商務用 Skype Server 2015 也支援下列舊版用戶端在執行 Mac os 10.5.8 或最新 service pack 或版本 (Intel) 作業系統 (Mac 作業系統10.9 作業系統的電腦上，) 目前不支援。 如需支援的功能的詳細資訊，請參閱[桌面用戶端的商務用 Skype 的功能比較](desktop-feature-comparison.md)。
  
- Microsoft Lync for Mac 2011 (請參閱 [Lync For mac 2011 部署指南](/previous-versions/office/office-for-mac-2011/jj984275(v=office.14))) 
    
- Microsoft Communicator for mac 2011 (請參閱[Communicator for mac 2011 部署指南](/previous-versions/office/office-for-mac-2011/jj984270(v=office.14))) 
 
商務用 Skype Server 2019 不支援這些用戶端。
   
## <a name="infrastructure-requirements-for-skype-for-business-on-mac"></a>Mac 上的商務用 Skype 基礎結構需求
<a name="Infrastructure"> </a>

Mac 用戶端的商務用 Skype 會利用整合通訊管理平臺 (UCMP) ，以及行動用戶端使用的整合通訊網頁 API (UCWA) 。
  
用戶端與我們的行動用戶端有相同的需求，因為您必須要有部署的 Access Edge Server 和反向 Proxy。 
  
### <a name="authentication"></a>驗證

Mac 用戶端上的商務用 Skype 支援以憑證為基礎的驗證、Microsoft 新式驗證，以及在部署及啟用時 Multi-Factor 驗證。
  
> [!NOTE]
> 由於目前的限制，使用者的 Exchange 認證必須與其商務用 Skype 認證相同。 
  
### <a name="certificates"></a>憑證

在 Access Edge 上使用的憑證，反向 Proxy 和前端伺服器不得使用 SHA-512 雜湊演算法。
  
必須定義及可供用戶端存取 HTTP 憑證吊銷清單。 例如，我們不支援憑證中的 LDAP 專案做為您的憑證吊銷清單。
  
### <a name="dns"></a>DNS

必須正確部署行動，Mac 用戶端上的商務用 Skype 才能正常運作。 常見的失敗案例是在內部網路上可解析下列兩個 DNS 專案：
  
- lyncdiscoverinternal.\<sipdomain\>
    
- lyncdiscover.\<sipdomain\>
    
如需詳細資訊，請參閱： [在 Lync server 2013 部署行動性](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mobility)，以及 [Microsoft Lync Server 2010 行動指南](https://go.microsoft.com/fwlink//p/?LinkId=798226)。
  
## <a name="see-also"></a>另請參閱
<a name="Infrastructure"> </a>

[商務用 Skype Server 的 DNS 需求](../../plan-your-deployment/network-requirements/dns.md)

[常見問題集](https://go.microsoft.com/fwlink/p/?LinkId=798227)
  
[已知問題](https://go.microsoft.com/fwlink/p/?LinkId=798228)