---
title: 在商務用 Skype 中規劃宣告應用程式
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
description: 在商務用 Skype Server Enterprise Voice 中規劃宣告應用程式，以設定組織中未指派電話號碼的電話通話方式。 包括音訊檔需求。
ms.openlocfilehash: b1929fa14b105fd8eccd0f178ae7ef77c1bdf086
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813753"
---
# <a name="plan-for-the-announcement-application-in-skype-for-business"></a>在商務用 Skype 中規劃宣告應用程式

在商務用 Skype Server Enterprise Voice 中規劃宣告應用程式，以設定組織中未指派電話號碼的電話通話方式。 包括音訊檔需求。

商務用 Skype 伺服器宣告應用程式可讓您設定撥打的電話號碼對您的組織有效，但未指派給使用者或電話的來電處理。 您可以將這些通話轉接至預先定義的目的地 (電話號碼、SIP URI 或語音信箱) 或播放音訊宣告或兩者。 宣告應用程式可協助您避免來電者 misdials 並聽到忙碌色調或 SIP 用戶端收到錯誤訊息的情況。 本節包含宣告應用程式特有的規劃資訊

當您部署宣告應用程式時，您必須設定未指派的號碼表，以決定當某人撥打未指派的號碼時要採取的動作。 「未指派的號碼」表包含對組織有效的電話號碼範圍，並指定哪個宣告應用程式會處理每個範圍。 當來電者撥打對您的組織有效的電話號碼，但未指派給任何人時，商務用 Skype Server 會查詢未指派號碼路由表中的號碼，識別該號碼屬於哪個範圍，並將通話路由傳送至該範圍所指定的宣告應用程式。 宣告應用程式會接聽來電，並 (如果將其設定為執行這項操作，則) 然後中斷通話，或將其轉接至預先決定的目的地，例如操作員。 您可以使用商務用 Skype Server 管理命令介面 Cmdlet 來設定多個音訊訊息，或傳送目的地。

設定未指派號碼表的方式取決於其使用方式。如果您有不再使用的特定號碼，而且想要播放專為各個號碼而設計的訊息，則可以在未指派號碼表中輸入那些特定號碼。例如，如果您變更了客戶服務中心的號碼，則可以輸入舊的客戶服務號碼，並將其與宣告相關聯，以提供新號碼。如果您想要對撥打未指派之號碼的任何人 (如離職員工) 播放一般訊息，則可以輸入您組織中所有有效分機的範圍。只要來電者撥打目前未指派的號碼，就會叫用未指派號碼表。

## <a name="deployment-and-requirements"></a>部署和需求

宣告應用程式會自動隨回應群組應用程式一起安裝。 宣告及回應群組應用程式是企業語音部署的標準元件：當您部署企業語音時，會自動部署這兩個應用程式。

### <a name="software-requirements"></a>軟體需求

執行宣告應用程式的所有前端伺服器或 Standard Edition 伺服器，都必須為執行 windows Server 2008 R2 的伺服器安裝 Windows Media Format Runtime，或為執行 Windows Server 2012 或 Windows Server 2012 R2 的伺服器安裝 Microsoft Media Foundation。 若為 Windows Server 2008 R2，Windows Media Format Runtime 會安裝為 Windows 桌面體驗的一部分。 Windows media Audio ( 的 windows media Format Runtime 或 Microsoft Media Foundation 是 Windows Media Audio 的必要功能。宣告應用程式針對宣告和音樂所播放的 wma) 檔案。

### <a name="port-requirements"></a>連接埠需求

宣告應用程式會使用 **埠 5071** 進行 SIP 聆聽要求。

> [!NOTE]
> 此埠是預設設定，您可以使用 **Set-CsApplicationServer** Cmdlet 進行變更。 如需此 Cmdlet 的詳細資訊，請參閱商務用 Skype Server 管理命令介面檔。

### <a name="audio-file-requirements"></a>音訊檔案需求

宣告應用程式支援波形 ( .wav) 檔案格式和 Windows Media 音訊)  ( 的音樂和宣告的檔案格式。 宣告應用程式的音訊檔需求與回應群組應用程式相同。 如需詳細資訊，請參閱 [回應群組的技術需求](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)。


