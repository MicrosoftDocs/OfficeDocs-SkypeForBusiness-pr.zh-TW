---
title: 為商務用 Skype Server 部署用戶端
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 摘要：商務用 Skype 的企業用戶端安裝方法的概述。
ms.openlocfilehash: ccaed5620c7f524a5a39fc6a35e6d688cd97a0eb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805693"
---
# <a name="deploy-clients-for-skype-for-business-server"></a>為商務用 Skype Server 部署用戶端
 
**摘要：** 商務用 Skype 之企業用戶端安裝方法的概述。
  
如何將商務用 Skype 部署至使用者，取決於您購買的商務用 skype 是否為 Microsoft 365 或 Office 365 方案的一部分，或是您購買的商務用 Skype 的大量授權版本。 
  
- **Microsoft 365 或 Office 365** 如果您有包含商務用 Skype 的 Microsoft 365 或 Office 365 方案，則使用的安裝技術稱為 Click-to-Run。 您可以讓您的使用者自行從 Microsoft 365 系統管理中心安裝商務用 Skype。 或者，您可以將軟體下載到您的本機網路，然後使用您現有的軟體部署工具，例如 Microsoft 端點 Configuration Manager，將商務用 Skype 部署至使用者。 如需 Microsoft 365 和 Office 365 隨附的商務用 Skype 相關安裝資訊，請參閱 [在 microsoft 365 或 office 365 中部署商務用 skype 用戶端](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)。
    
- **大量授權** 如果您有大量授權版本的商務用 Skype 2015 或2016用戶端，則使用的安裝技術為 Windows Installer (MSI) 。 Windows Installer 型安裝套件是由多個 MSI 檔案所組成。 中性語言核心 MSI 套件結合了一或多個特定語言套件，組成完整的產品。 安裝程式組合了個別套件，在安裝 Office 於使用者的電腦期間 (以及之後)，執行自訂與維護工作。 商務用 Skype 2019 用戶端使用 Click-to-Run 安裝程式。
    
本節中的主題說明如何使用和自訂 Windows 安裝程式，透過您的一般程式，將商務用 Skype 用戶端部署至使用者。
  
> [!NOTE]
> Microsoft Office 的 Skype 會議增益集（支援 Outlook 郵件和共同作業用戶端中的會議管理）會自動安裝商務用 Skype 用戶端。 
  
> [!NOTE]
> Microsoft 365 和 Office 365 安裝程式不會卸載舊版的 Lync。 商務用 Skype 用戶端會與其他 Lync 用戶端同時安裝。 
  
## <a name="installing-windows-clients"></a>安裝 Windows 用戶端

- [在商務用 Skype Server 中自訂 Windows 用戶端安裝](customize-windows-client-installation.md)
    
- [使用商務用 Skype 設定用戶端經驗](configure-the-client-experience.md)
    
- [在商務用 Skype Server 中設定智慧連絡人清單](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a>安裝裝置用戶端

- [安裝並測試適用于 Windows Phone 的商務用 Skype](windows-phone.md)
    
- [安裝及測試 iOS 的商務用 Skype](ios.md)
    
    
- [使用商務用 Skype Server 部署 Lync VDI 外掛程式](deploy-the-lync-vdi-plug-in.md)
    
- [在商務用 Skype Server 中部署 Web 可下載的用戶端](deploy-web-downloadable-clients.md)
    
- [在商務用 Skype 中自訂 Mac 用戶端體驗](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a>另請參閱

[在 Microsoft 365 或 Office 365 中部署商務用 Skype 用戶端](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
