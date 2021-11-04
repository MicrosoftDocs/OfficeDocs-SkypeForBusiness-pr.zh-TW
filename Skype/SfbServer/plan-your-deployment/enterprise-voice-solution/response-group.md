---
title: 在商務用 Skype Server 中規劃回應群組應用程式
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6cc333e7-4029-4372-86b2-016040c415fb
description: 在商務用 Skype Server 企業語音中規劃回應群組，可讓您設定使用者群組的呼叫路由。 包括音訊檔需求。
ms.openlocfilehash: 3ca8159ca3d6fc37aa5c8f1f3f88f8188929f71f
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767551"
---
# <a name="plan-for-the-response-group-application-in-skype-for-business-server"></a>在商務用 Skype Server 中規劃回應群組應用程式

在商務用 Skype Server 企業語音中規劃回應群組，可讓您設定使用者群組的呼叫路由。 包括音訊檔需求。

如果您的組織擁有接聽和管理特定通話類型的人員群組，例如，針對客戶服務、內部服務台或部門的一般電話支援，您可以部署回應群組應用程式來管理這些通話類型。 回應群組應用程式會將來電路由和佇列傳送給指定的人員（稱為代理人）。 藉由使用回應群組，您可以增加電話支援服務的使用頻率，並減少為執行這些服務所產生的負荷。

來電者與回應群組通話時，該通話會根據群組搜尋或來電者對互動語音回應 (IVR) 問題的回答，路由傳送給代理人。 回應群組應用程式會使用標準回應群組路由方法，將通話路由傳送至下一個可用的代理程式。 支援的呼叫路由方法包括串列、最長閒置、平行、迴圈和接聽路由 (也就是說，不論其目前狀態為何，所有的代理程式都會同時呼叫給每一個來電) 。

如果沒有代理人有空，則會將通話保留在佇列中，直到某位代理人有空。 通話保留在佇列時，來電者會聽到音樂，直到某位有空的代理人受理該通話。 若佇列已滿，或是佇列中的呼叫超時，來電者可能會聽到訊息，然後中斷連線或轉接至不同的目的地，例如不同的電話號碼或語音信箱。 依系統管理員設定回應群組的方式不同，代理人受理通話時，來電者不一定會看到代理人的身分識別。 代理人得以正式方式受理通話 (表示他們必須先登入群組，才能受理路由傳送給群組的通話)，或以非正式方式受理通話 (表示他們未登入及登出群組就受理通話)。

> [!NOTE]
> 只有內部部署的使用者可以成為代理人。如果將代理人從內部部署移至線上，回應群組電話將無法路由傳送給該代理人。

> [!NOTE]
> 回應群組應用程式使用稱為「符合」的內部服務，以佇列通話並尋找可用的代理程式。 每一部執行回應群組應用程式的電腦都會執行相符服務，但是一次只能有一個符合每個集區的服務--另一個是被動。 如果主動配對服務在意外中斷服務期間無法使用，則被動配對服務其中之一會變成主動配對服務。 回應群組應用程式會盡力確保通話路由和佇列繼續不間斷地繼續進行。 但是在轉換配對服務時，所有轉接中的通話都會中斷。 例如，如果轉換是由於前端伺服器即將停機，則目前正由使用中的相符服務所處理的所有呼叫都會遺失該前端伺服器上的服務。

## <a name="response-group-workflows"></a>回應群組工作流程

工作流程會定義從電話鈴聲開始響起到有人接聽該通電話這段時間的呼叫行為。工作流程指定了用於保留通話的佇列，並指定用於群組搜尋的路由方法，或讓互動回應群組使用的問題和回答。工作流程也定義歡迎訊息、等候音樂、上班時間和假日之類的設定值。

> [!NOTE]
> 您必須先建立代理群組和佇列，再建立使用這些項目的工作流程。

## <a name="management-of-response-groups"></a>管理回應群組

在商務用 Skype Server 中，可以使用兩個管理角色來管理回應群組：回應群組管理員及回應群組管理員。 回應群組管理員可以管理任何回應群組的任何方面。 回應群組管理員只可管理特定的部分，而且只可管理其擁有的回應群組。 管理員角色可協助您降低管理成本，因為您可以將特定回應群組的有限責任委派給已啟用企業語音的任何使用者。 請注意，使用者可以是回應群組管理員和回應群組管理員。

為了容納管理員角色，回應群組應用程式使用 Managed 或未受管理的 **工作流程類型** 。 下表描述「已受管理」與「未受管理」回應群組內容。

**受管理與未受管理回應群組**

|**回應群組類型**|**描述**|
|:-----|:-----|
|非 託管  <br/> | 未受管理的回應群組沒有指定的管理員。 只有回應群組管理員可以設定這些回應群組。 <br/>  多個未受管理回應群組可共用一個佇列或代理人群組。 <br/>  當您將回應群組從先前版本遷移至商務用 Skype Server 時，此類型會設定為 [未管理]。 <br/> |
|受管理  <br/> | 回應群組管理員可以設定受管理回應群組的任何方面。 <br/>  回應群組管理員無法查看或修改未明確指派給他們的回應群組。 <br/>  回應群組管理員可以只為明確指派給他們的回應群組設定部分設定。 <br/>  受管理的回應群組無法與其他任何受管理或未受管理的回應群組共用任何佇列或代理人群組。 <br/> |

下表說明回應群組管理員可對指派給他們的回應群組執行和無法執行的動作。

**回應群組管理員功能**

|**可設定：**|**可建立、刪除或設定：**|**不能：**|
|:-----|:-----|:-----|
| Agents <br/>  歡迎訊息 <br/>  回應群組名稱 <br/>  描述 <br/>  顯示號碼 <br/>  營業時間 <br/>  保留音樂 <br/>  狀態 (使用中/非使用中) <br/>  群組搜尋工作流程或互動語音回應 (IVR) 工作流程 <br/> | 代理人群組 <br/>  佇列 <br/>  假日集 <br/> | 建立或刪除任何工作流程類型 <br/>  修改核心回應群組設定，例如：**[SIP URI]**、**[電話號碼]** 或 **[工作流程類型]**。  <br/> |

回應群組管理員可使用下列工具來管理其指定的回應群組。

- 商務用 Skype Server 控制台

    > [!NOTE]
    > 回應群組管理員只能使用此工具來管理回應群組設定。 其他的商務用 Skype Server 設定無法供管理員使用。

- 回應群組設定工具

- 商務用 Skype Server 管理命令介面

回應群組可非常適合部門或工作組環境 (如需詳細資訊，請參閱 [容量規劃，以進行回應群組](/previous-versions/office/lync-server-2013/lync-server-2013-capacity-planning-for-response-group)) ，而且可以部署于全新的電話語音安裝中。 它支援來自企業語音部署和本機電信公司網路的撥入電話。 代理程式可使用商務用 Skype、lync 2013、lync 2010、lync 2010 語音應答或 lync 電話 Edition，將通話路由傳送給他們。

## <a name="deployment-and-requirements"></a>部署和需求

當您部署企業語音時，會自動啟用回應群組應用程式。

### <a name="hardware-and-software-requirements"></a>硬體及軟體需求

回應群組應用程式與前端伺服器具有相同的硬體需求、作業系統需求和軟體必要條件。

如果您使用 Windows 媒體音訊)  ( 回應群組音樂和宣告，所有前端伺服器或所有執行回應群組應用程式的 Standard edition 伺服器，都必須為執行 Windows Server 2008 R2 的伺服器安裝 Windows 媒體格式執行時間，或執行 Windows Server 2012 o 之伺服器的 Microsoft Media Foundationr Windows Server 2012 R2。 針對 Windows Server 2008 R2，Windows Media Format Runtime 是以 Windows 桌面體驗的一部分安裝。

回應群組使用 **語言套件** 來支援文字語音語音及語音辨識。 在您設定訊息 (如歡迎訊息與其他提示) 以及互動式語音回應 (IVR) 的問題與回答時，都會用到這些語音技術。 根據預設，在您部署商務用 Skype Server 時會安裝26支援的語言套件。

### <a name="port-requirements"></a>連接埠需求

回應群組應用程式使用下列埠：

- 用於 SIP 聆聽要求的 **埠 5071**

- 用於伺服器間通訊的 **埠 8404**

    > [!NOTE]
    > 此埠用於配對服務，且在具有多部前端伺服器的集區中部署回應群組應用程式時是必要的。

   > [!NOTE]
   > 這些連接埠為預設設定，可使用 **Set-CsApplicationServer** Cmdlet 予以變更。 如需此 Cmdlet 的詳細資訊，請參閱商務用 Skype Server 管理命令介面檔。

### <a name="audio-file-requirements"></a>音訊檔案需求

回應群組應用程式支援波形 ( wav) 檔案格式，以及 Windows 媒體音訊 ( 的回應群組訊息、等候音樂或互動語音回應的檔案格式) IVR (問題。

Windows 媒體音訊檔案格式要求在執行 Windows Server 2008 R2 和 Windows server 2008 的前端伺服器上安裝 Windows 媒體格式執行時間。 如需詳細資訊，請參閱本節稍早的＜軟體需求＞。

#### <a name="supported-wave-file-formats"></a>支援的 Wave 檔案格式

所有 Wave 檔案必須符合下列需求：

- 8 位元或 16 位元檔案

- 線性脈衝代碼調變 (LPCM)，A-Law 或 mu-Law 格式

- 單音或立體聲

- 4MB 以下

為使 Wave 檔案有最佳表現，建議使用 16 kHz 單音的 16 位元 Wave 檔案。

#### <a name="supported-windows-media-audio-file-formats"></a>支援的 Windows Media 音訊檔案格式

如果您使用 Windows Media 音訊檔案，請考慮使用低位元速率，並驗證系統承受負載時的效能。

您可以使用 Microsoft Expression Encoder 4 將檔案轉換成 Windows Media Audio 格式。 若要下載運算式編碼器4，請參閱 [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkId=202843) 。

### <a name="response-group-configuration-tool-requirements"></a>回應群組設定工具需求

回應群組設定工具支援下表所述之作業系統和網頁瀏覽器的組合。

> [!NOTE]
> 支援 32 位元或 64 位元版本的作業系統。只支援 32 位元版本的 Internet Explorer。

**支援的作業系統和網頁瀏覽器**

|**作業系統**|**網頁瀏覽器**|
|:-----|:-----|
|Windows Vista Service Pack (SP) 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (原生模式)  <br/> Internet Explorer 9 (原生模式)  <br/> |
|Windows 7  <br/> Windows 7 Service Pack 1  <br/> |Internet Explorer 8 (原生模式)  <br/> Internet Explorer 9 (原生模式)  <br/> |
|Windows Server 2008 Service Pack 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (原生模式)  <br/> Internet Explorer 9 (原生模式)  <br/> |
|Windows Server 2008 R2  <br/> Windows Server 2008 R2 Service Pack 1  <br/> |Internet Explorer 8 (原生模式)  <br/> Internet Explorer 9 (原生模式)  <br/> |
|Windows Server 2012  <br/> ||
|Windows Server 2012 R2  <br/> ||

### <a name="response-group-agent-console"></a>回應群組代理程式主控台

代理程式主控台支援下表中所述之作業系統和網頁瀏覽器的組合。

> [!NOTE]
> 支援 32 位元或 64 位元版本的作業系統。只支援 32 位元版本的 Internet Explorer。

**支援的作業系統和網頁瀏覽器**

|**作業系統**|**網頁瀏覽器**|
|:-----|:-----|
|Windows Vista Service Pack (SP) 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (原生模式)  <br/> Internet Explorer 9 (原生模式)  <br/> |
|Windows 7  <br/> Windows 7 Service Pack 1  <br/> |Internet Explorer 8 (原生模式)  <br/> Internet Explorer 9 (原生模式)  <br/> Firefox 10.0  <br/> Chrome 18.0  <br/> |
|Windows Server 2008 Service Pack 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (原生模式)  <br/> Internet Explorer 9 (原生模式)  <br/> |
|Windows Server 2008 R2  <br/> Windows Server 2008 R2 Service Pack 1  <br/> |Internet Explorer 8 (原生模式)  <br/> Internet Explorer 9 (原生模式)  <br/> Firefox 10.0  <br/> Chrome 18.0  <br/> |
|Windows Server 2012  <br/> |
|Windows Server 2012 R2  <br/> |

## <a name="client-support"></a>用戶端支援

回應群組應用程式支援下列用戶端：

- 商務用 Skype 桌面用戶端

- Lync 2013 桌面用戶端

- Lync 2010 桌面用戶端

- Lync 2010 Attendant

- Office通訊伺服器 2007 R2 助理

- Lync Phone Edition

> [!NOTE]
> Lync mobile 用戶端不支援回應群組應用程式。

您可以使用的特定用戶端取決於您所使用的回應群組使用者類型：

- 來電 **者可以使用** 之前所列的任何用戶端，以及透過公用交換電話網路 (PSTN) 中的標準電話，撥打回應群組。

- 不會登入和登出其群組以接受來電的 **非正式代理** (，) 可以使用語音應答、Lync 或 lync 電話 Edition 接受通話。 非正式代理程式會在他們使用其中一位用戶端登入商務用 Skype Server 時，自動登入他們的群組。

- 必須用來登入和登出其群組的 **正式代理** (代理商可以使用商務用 Skype 和存取代理程式主控台的功能表項目目，或是直接從 Internet Explorer 存取代理程式主控台，以接受通話) 。

## <a name="capacity-planning"></a>容量規劃

下表說明您可以用來作為容量規劃需求之基礎的回應群組使用者模型。

> [!NOTE]
> 下表中的數位是假設您使用 16 kHz、mono、16位 ( 波形) 所有回應群組音訊檔案的檔案。 如果您使用其他檔案格式，例如 Windows 媒體音訊 ( .wma) ，這些數位可能會有所不同。

> [!IMPORTANT]
> 請記住，針對嚴重損壞修復容量規劃，配對集區的每個集區都應該可以處理兩個集區中所有回應群組的工作量。

**回應群組使用者模型**

|**計量**|**每 Enterprise Edition <br/> 包含8部前端伺服器的集區 ()**|**根據 Standard Edition 伺服器**|
|:-----|:-----|:-----|
|每秒來電數  <br/> |16   <br/> |第  <br/> |
|連線至 IVR 或 MoH 的並行通話  <br/> |480  <br/> |60  <br/> |
| (沒有 IM) 的併發匿名會話  <br/> |224  <br/> |日  <br/> |
|使用 IM)  (同時匿名會話  <br/> |64  <br/> |8   <br/> |
|主動代理 (正式和非正式)   <br/> |2400  <br/> |2400  <br/> |
|群組搜尋數目  <br/> |800  <br/> |800  <br/> |
|IVR 群組 (使用語音辨識的數目)   <br/> |400  <br/> |400  <br/> |