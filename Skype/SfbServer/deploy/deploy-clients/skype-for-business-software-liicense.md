---
title: Skype 會議室系統商務用 Skype 軟體授權
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: 閱讀此主題以瞭解如何檢查您是否有商務用 Skype 的軟體大量授權。
ms.openlocfilehash: 0e8fcc9b4dc9dec481af7b0a1d976d590c40def0
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62399987"
---
# <a name="skype-room-system-skype-for-business-software-license"></a>Skype 會議室系統：商務用 Skype 軟體授權
 
閱讀此主題以瞭解如何檢查您是否有商務用 Skype 的軟體大量授權。 
  
Skype 會議室系統會使用已安裝的商務用 Skype 用戶端，這需要軟體大量授權。 部署第一部 Skype 的會議室系統之前，請先使用金鑰管理伺服器 (KMS) 或多個啟用機碼 (MAK) ，以瞭解部署的大量授權狀態。
  
## <a name="key-management-servers-kms"></a> (KMS 金鑰管理伺服器) 

如果 KMS 已到位，且將散佈商務用 Skype 大量授權啟用，Skype 的會議室系統會自動啟用商務用 Skype 用戶端。 若要找出 KMS 是否正確：
  
在命令提示字元下，執行：  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`
  
若要設定 KMS，請參閱[KMS 啟用 Office 2013](/previous-versions/office/office-2013-resource-kit/ee624357(v=office.15))和[gvlk，以進行 KMS 和 Active Directory 啟用 Office 2013](/DeployOffice/vlactivation/gvlks)
  
Office 2013 的通用大量授權金鑰，適用于 Lync： 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (此機碼會導致 Skype 的會議室系統在網路上尋找 KMS。 ) 
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a>從大量授權服務中心 (MAK) 的多重啟用金鑰 (VLSC) 

如果客戶使用任何其他大量授權軟體，IT 部門將使用 VLSC 來管理軟體啟用和大量授權合約 (VLA) 。 這也可讓公司購買商務用 Skype VL 啟用，之後公司可以在 Skype 室系統管理主控台中取得 MAK 以進行輸入。
  
具有 VLA 的客戶必須知道其 VLSC 認證，其將用來管理合約並取得 MAK。 如果不確定，客戶的財務部門應該可以確認客戶是否已支付 VLA。
  
若要取得 MAK，請存取大量授權服務中心，以查看協定，並下載 (MAK) 中的產品金鑰。 如需詳細資訊，請移至 [大量授權服務中心](https://www.microsoft.com/Licensing/servicecenter/default.aspx)。 
  
## <a name="mak-for-microsoft-365-or-office-365-without-vlsc-access"></a>不具備 VLSC 存取權的 Microsoft 365 或 Office 365 的 MAK

若客戶沒有大量授權合約，商務用 Skype 啟用會比較難管理。 不過，如果沒有 VLSC 存取權，Microsoft 365 和 Office 365 客戶可以透過提供下列資訊，針對銷售 Skype 室系統的 OEM，獲得促銷 MAK：
  
- 公司名稱
    
- 部署連絡人名稱、電子郵件和電話號碼
    
- 部署的系統數目
    
- 部署日期
    
- 如果客戶有 Microsoft 技術客戶經理，TAM 的名稱和連絡人資訊
