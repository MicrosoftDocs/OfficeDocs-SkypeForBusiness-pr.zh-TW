---
title: Skype 會議室系統商務用 Skype 軟體授權
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: 請閱讀本主題，瞭解如何檢查您是否擁有商務用 Skype 軟體大量授權。
ms.openlocfilehash: 5de1fc9204e22b30431f692770e3ec663599dd73
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768476"
---
# <a name="skype-room-system-skype-for-business-software-license"></a>Skype 會議室系統：商務用 Skype 軟體授權
 
請閱讀本主題，瞭解如何檢查您是否擁有商務用 Skype 軟體大量授權。 
  
Skype 室系統會使用已安裝的商務用 Skype 用戶端，這需要軟體大量授權。 在部署第一個 Skype 房間系統之前，請先瞭解部署的大量授權狀態-使用金鑰管理伺服器（KMS）或多個啟用金鑰（MAK）。
  
## <a name="key-management-servers-kms"></a>金鑰管理伺服器（KMS）

如果 KMS 位於適當位置，且將發佈商務用 Skype 大量授權啟用，Skype 會議室系統會自動啟動商務用 Skype 用戶端。 若要瞭解 KMS 是否已就緒：
  
從命令提示字元執行：`nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`
  
如需詳細資訊，請參閱[如何透過 DNS 探索 Office 和 WINDOWS KMS 主機，並移除未授權的實例](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx)。 
  
若要設定 KMS，請參閱[office 2013](https://technet.microsoft.com/library/ee624357.aspx)和 GVLKs 的 kms 啟用（[適用于 kms 以及 Office 2013 的 Active Directory 啟用](https://technet.microsoft.com/library/dn385360.aspx)）
  
Lync 的 Office 2013 一般大量授權金鑰： 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R （這個按鍵會使 Skype 會議室系統在網路上尋找 KMS）。
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a>大量授權服務中心（VLSC）的多個啟用金鑰（MAK）

如果客戶使用任何其他的大量授權軟體，IT 部門就會使用 VLSC 來管理軟體啟用和大量授權合約（VLA）。 這也會讓公司購買商務用 Skype VL 啟用，之後公司就可以取得 MAK 來在 Skype 會議室系統管理主控台中進行輸入。
  
擁有 VLA 的客戶必須知道他們的 VLSC 認證，這會用來管理合約及取得 MAK。 如果不確定，客戶的財務部門應該可以確認客戶是否已支付 VLA。
  
若要取得 MAK，請存取大量授權服務中心來查看協定，並下載產品金鑰（MAK）。 如需詳細資訊，請移至[大量授權服務中心](https://www.microsoft.com/Licensing/servicecenter/default.aspx)。 
  
## <a name="mak-for-office-365-without-vlsc-access"></a>Office 365 的 MAK，沒有 VLSC 存取權

如果客戶沒有大量授權協定，商務用 Skype 啟用的難度就會變得更難管理。 不過，沒有 VLSC 存取權的 Office 365 客戶可以提供下列資訊給 OEM 出售 Skype 會議室系統，以取得促銷 MAK：
  
- 公司名稱
    
- 部署連絡人名稱、電子郵件和電話號碼
    
- 部署的系統數量
    
- 部署日期
    
- 如果客戶擁有 Microsoft 技術客戶管理員，TAM 的名稱和連絡人資訊
    

