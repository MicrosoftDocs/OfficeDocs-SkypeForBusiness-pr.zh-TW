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
description: 閱讀此主題以瞭解如何檢查您是否有商務用 Skype 軟體大量授權。
ms.openlocfilehash: a44e95d8cd488e2b12e03ee9848ef3d1b254180c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220923"
---
# <a name="skype-room-system-skype-for-business-software-license"></a>Skype 聊天室系統：商務用 Skype 軟體授權
 
閱讀此主題以瞭解如何檢查您是否有商務用 Skype 軟體大量授權。 
  
Skype 室系統會使用已安裝的商務用 Skype 用戶端，這需要軟體大量授權。 部署第一個 Skype 室系統之前，請先瞭解部署的大量授權狀態-使用金鑰管理伺服器（KMS）或多重啟用金鑰（MAK）。
  
## <a name="key-management-servers-kms"></a>金鑰管理伺服器（KMS）

如果 KMS 已到位，且將散佈商務用 Skype 大量授權啟用，Skype 會議室系統會自動啟用商務用 Skype 用戶端。 若要找出 KMS 是否已到位：
  
在命令提示字元下，執行：`nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`
  
如需詳細資訊，請參閱 how [to 透過 DNS 探索 Office 和 WINDOWS KMS 主機，並移除未授權的實例](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx)。 
  
若要設定 KMS，請參閱[office 2013](https://technet.microsoft.com/library/ee624357.aspx)和 Gvlk 的 kms 啟用，[以取得 OFFICE 2013 的 Kms 和 Active Directory 啟用](https://technet.microsoft.com/library/dn385360.aspx)
  
適用于 Lync 的 Office 2013 一般大量授權金鑰： 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R （此機碼會使 Skype 會議室系統在網路上尋找 KMS）。
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a>大量授權服務中心（VLSC）的多重啟用金鑰（MAK）

如果客戶使用任何其他大量授權軟體，IT 部門將使用 VLSC 管理軟體啟用和大量授權合約（VLA）。 這也會讓公司購買商務用 Skype VL 啟用，在此期間，公司可以取得 MAK 以供 Skype 聊天室系統管理主控台中輸入。
  
具有 VLA 的客戶必須知道其 VLSC 認證，其將用來管理合約並取得 MAK。 如果不確定，客戶的財務部門應該可以確認客戶是否已支付 VLA。
  
若要取得 MAK，請存取大量授權服務中心以查看協定和下載產品金鑰（MAK）。 如需詳細資訊，請移至[大量授權服務中心](https://www.microsoft.com/Licensing/servicecenter/default.aspx)。 
  
## <a name="mak-for-microsoft-365-or-office-365-without-vlsc-access"></a>不含 VLSC 存取權的 Microsoft 365 或 Office 365 的 MAK

若客戶沒有大量授權合約，商務用 Skype 啟用將會困難許多。 不過，沒有 VLSC 存取權的 Microsoft 365 和 Office 365 客戶可以透過提供下列資訊，針對銷售 Skype 室系統的 OEM，取得促銷 MAK：
  
- 公司名稱
    
- 部署連絡人名稱、電子郵件和電話號碼
    
- 部署的系統數目
    
- 部署日期
    
- 如果客戶有 Microsoft 技術客戶經理，TAM 的名稱和連絡人資訊
    

