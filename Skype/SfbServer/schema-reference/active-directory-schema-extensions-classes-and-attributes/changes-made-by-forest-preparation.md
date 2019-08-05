---
title: 在商務用 Skype Server 的 [目錄林準備] 中所做的變更
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
description: 本節說明全域設定與物件, 以及由目錄林準備步驟所建立的泛型服務和管理群組。
ms.openlocfilehash: ece4a9bd1db5f43b52a96265dee41ee3a0a30b22
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192923"
---
# <a name="changes-made-by-forest-preparation-in-skype-for-business-server"></a><span data-ttu-id="f963f-103">在商務用 Skype Server 的 [目錄林準備] 中所做的變更</span><span class="sxs-lookup"><span data-stu-id="f963f-103">Changes made by forest preparation in Skype for Business Server</span></span>

<span data-ttu-id="f963f-104">本節說明全域設定與物件, 以及由目錄林準備步驟所建立的泛型服務和管理群組。</span><span class="sxs-lookup"><span data-stu-id="f963f-104">This section describes the global settings and objects, and the universal service and administration groups that are created by the forest preparation step.</span></span>

## <a name="active-directory-global-settings-and-objects"></a><span data-ttu-id="f963f-105">Active Directory 全域設定與物件</span><span class="sxs-lookup"><span data-stu-id="f963f-105">Active Directory Global Settings and Objects</span></span>

<span data-ttu-id="f963f-106">如果您在配置容器中儲存全域設定 (所有新的商務用 Skype 伺服器部署都一樣), 目錄林準備就會使用現有的服務容器, 並在 Configuration\Services 下新增**RTC 服務**物件。面向.</span><span class="sxs-lookup"><span data-stu-id="f963f-106">If you store global settings in the Configuration container (as is the case for all new Skype for Business Server deployments), forest preparation uses the existing Services container and adds an **RTC Service** object under the Configuration\Services object.</span></span> <span data-ttu-id="f963f-107">在 RTC 服務物件下, 林準備會新增 type msRTCSIP-GlobalContainer 的**全域設定**物件。</span><span class="sxs-lookup"><span data-stu-id="f963f-107">Under the RTC Service object, forest preparation adds a **Global Settings** object of type msRTCSIP-GlobalContainer.</span></span> <span data-ttu-id="f963f-108">[全域設定] 物件包含所有適用于商務用 Skype Server 部署的設定。</span><span class="sxs-lookup"><span data-stu-id="f963f-108">The global settings object holds all the settings that apply to the Skype for Business Server deployment.</span></span> <span data-ttu-id="f963f-109">如果您在系統容器中儲存全域設定, 目錄林準備會在 System\Microsoft 物件的根網域系統容器和 RTC 服務物件下使用 Microsoft 容器。</span><span class="sxs-lookup"><span data-stu-id="f963f-109">If you store global settings in the System container, forest preparation uses a Microsoft container under the root domain System container and an RTC Service object under the System\Microsoft object.</span></span>

<span data-ttu-id="f963f-110">林準備也會為執行程式的根網域新增一個新**的 msRTCSIP-網域**物件。</span><span class="sxs-lookup"><span data-stu-id="f963f-110">Forest preparation also adds a new **msRTCSIP-Domain** object for the root domain in which the procedure is run.</span></span>

## <a name="active-directory-universal-service-and-administration-groups"></a><span data-ttu-id="f963f-111">Active Directory 泛型服務與管理群組</span><span class="sxs-lookup"><span data-stu-id="f963f-111">Active Directory Universal Service and Administration Groups</span></span>

<span data-ttu-id="f963f-112">林準備會根據您指定的網域建立通用群組, 並新增這些群組的存取控制專案 (Ace)。</span><span class="sxs-lookup"><span data-stu-id="f963f-112">Forest preparation creates universal groups based on the domain that you specify and adds access control entries (ACEs) for these groups.</span></span> <span data-ttu-id="f963f-113">此步驟會在您指定之網域的使用者容器中建立通用群組。</span><span class="sxs-lookup"><span data-stu-id="f963f-113">This step creates the universal groups in the User containers of the domain that you specify.</span></span>

<span data-ttu-id="f963f-114">通用群組可讓系統管理員存取及管理全域設定及服務。</span><span class="sxs-lookup"><span data-stu-id="f963f-114">Universal groups allow administrators to access and manage global settings and services.</span></span> <span data-ttu-id="f963f-115">[林準備] 會新增下列類型的通用群組:</span><span class="sxs-lookup"><span data-stu-id="f963f-115">Forest preparation adds the following types of universal groups:</span></span>

- <span data-ttu-id="f963f-116">系統**管理群組**這些群組會定義商務用 Skype Server 網路的系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="f963f-116">**Administrative groups** These groups define administrator roles for a Skype for Business Server network.</span></span>

- <span data-ttu-id="f963f-117">**基礎結構群組**這些群組提供存取商務用 Skype Server 基礎結構特定區域的許可權。</span><span class="sxs-lookup"><span data-stu-id="f963f-117">**Infrastructure groups** These groups provide permission to access specific areas of the Skype for Business Server infrastructure.</span></span> <span data-ttu-id="f963f-118">它們的功能是系統管理群組的元件。</span><span class="sxs-lookup"><span data-stu-id="f963f-118">They function as components of administrative groups.</span></span> <span data-ttu-id="f963f-119">您不應該修改這些群組, 或直接將使用者新增至其中。</span><span class="sxs-lookup"><span data-stu-id="f963f-119">You should not modify these groups or add users directly to them.</span></span>

- <span data-ttu-id="f963f-120">**服務群組**這些群組是存取各種商務用 Skype Server 服務所需的服務帳戶。</span><span class="sxs-lookup"><span data-stu-id="f963f-120">**Service groups** These groups are service accounts that are required to access various Skype for Business Server services.</span></span>

<span data-ttu-id="f963f-121">下表說明管理群組。</span><span class="sxs-lookup"><span data-stu-id="f963f-121">The following table describes the administrative groups.</span></span>

<span data-ttu-id="f963f-122">**在林準備期間建立的系統管理群組**</span><span class="sxs-lookup"><span data-stu-id="f963f-122">**Administrative Groups Created During Forest Preparation**</span></span>

|<span data-ttu-id="f963f-123">**系統管理群組**</span><span class="sxs-lookup"><span data-stu-id="f963f-123">**Administrative group**</span></span>|<span data-ttu-id="f963f-124">**說明**</span><span class="sxs-lookup"><span data-stu-id="f963f-124">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f963f-125">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="f963f-125">RTCUniversalServerAdmins</span></span>  <br/> |<span data-ttu-id="f963f-126">允許成員管理伺服器和池設定, 包括所有伺服器角色、全域設定和使用者。</span><span class="sxs-lookup"><span data-stu-id="f963f-126">Allows members to manage server and pool settings, including all server roles, global settings, and users.</span></span>  <br/> |
|<span data-ttu-id="f963f-127">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="f963f-127">RTCUniversalUserAdmins</span></span>  <br/> |<span data-ttu-id="f963f-128">允許成員管理使用者設定, 以及將使用者從一個伺服器或一個池移到另一個伺服器或資源庫。</span><span class="sxs-lookup"><span data-stu-id="f963f-128">Allows members to manage user settings and move users from one server or pool to another.</span></span>  <br/> |
|<span data-ttu-id="f963f-129">RTCUniversalReadOnlyAdmins</span><span class="sxs-lookup"><span data-stu-id="f963f-129">RTCUniversalReadOnlyAdmins</span></span>  <br/> |<span data-ttu-id="f963f-130">允許成員讀取伺服器、池及使用者設定。</span><span class="sxs-lookup"><span data-stu-id="f963f-130">Allows members to read server, pool, and user settings.</span></span>  <br/> |

<span data-ttu-id="f963f-131">下表說明基礎結構群組。</span><span class="sxs-lookup"><span data-stu-id="f963f-131">The following table describes the infrastructure groups.</span></span>

<span data-ttu-id="f963f-132">**在林準備期間建立的基礎結構群組**</span><span class="sxs-lookup"><span data-stu-id="f963f-132">**Infrastructure Groups Created During Forest Preparation**</span></span>

|<span data-ttu-id="f963f-133">**基礎結構群組**</span><span class="sxs-lookup"><span data-stu-id="f963f-133">**Infrastructure group**</span></span>|<span data-ttu-id="f963f-134">**說明**</span><span class="sxs-lookup"><span data-stu-id="f963f-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f963f-135">RTCUniversalGlobalWriteGroup</span><span class="sxs-lookup"><span data-stu-id="f963f-135">RTCUniversalGlobalWriteGroup</span></span>  <br/> |<span data-ttu-id="f963f-136">授與商務用 Skype Server 全域設定物件的寫入權限。</span><span class="sxs-lookup"><span data-stu-id="f963f-136">Grants write access to global setting objects for Skype for Business Server.</span></span>  <br/> |
|<span data-ttu-id="f963f-137">RTCUniversalGlobalReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="f963f-137">RTCUniversalGlobalReadOnlyGroup</span></span>  <br/> |<span data-ttu-id="f963f-138">授與商務用 Skype Server 全域設定物件的唯讀存取權。</span><span class="sxs-lookup"><span data-stu-id="f963f-138">Grants read-only access to global setting objects for Skype for Business Server.</span></span>  <br/> |
|<span data-ttu-id="f963f-139">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="f963f-139">RTCUniversalUserReadOnlyGroup</span></span>  <br/> |<span data-ttu-id="f963f-140">授與商務用 Skype Server 使用者設定的唯讀存取權。</span><span class="sxs-lookup"><span data-stu-id="f963f-140">Grants read-only access to Skype for Business Server user settings.</span></span>  <br/> |
|<span data-ttu-id="f963f-141">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="f963f-141">RTCUniversalServerReadOnlyGroup</span></span>  <br/> |<span data-ttu-id="f963f-142">授與商務用 Skype Server 設定的唯讀存取權。</span><span class="sxs-lookup"><span data-stu-id="f963f-142">Grants read-only access to Skype for Business Server settings.</span></span> <span data-ttu-id="f963f-143">這個群組無法存取 [池] 層級設定, 只適用于個別伺服器專用的設定。</span><span class="sxs-lookup"><span data-stu-id="f963f-143">This group does not have access to pool level settings, only to settings specific to an individual server.</span></span>  <br/> |
|<span data-ttu-id="f963f-144">RTCUniversalSBATechnicians</span><span class="sxs-lookup"><span data-stu-id="f963f-144">RTCUniversalSBATechnicians</span></span>  <br/> |<span data-ttu-id="f963f-145">授與商務用 Skype Server 設定的唯讀存取權, 並放在安裝期間 survivable 分支裝置的 [本機管理員] 群組中。</span><span class="sxs-lookup"><span data-stu-id="f963f-145">Grants read-only access to Skype for Business Server configuration and are placed in the Local Administrators group of the survivable branch appliances during installation.</span></span>  <br/> |

<span data-ttu-id="f963f-146">下表說明服務群組。</span><span class="sxs-lookup"><span data-stu-id="f963f-146">The following table describes the service groups.</span></span>

<span data-ttu-id="f963f-147">**在林準備期間建立的服務群組**</span><span class="sxs-lookup"><span data-stu-id="f963f-147">**Service Groups Created During Forest Preparation**</span></span>

|<span data-ttu-id="f963f-148">**服務群組**</span><span class="sxs-lookup"><span data-stu-id="f963f-148">**Service group**</span></span>|<span data-ttu-id="f963f-149">**說明**</span><span class="sxs-lookup"><span data-stu-id="f963f-149">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f963f-150">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="f963f-150">RTCHSUniversalServices</span></span>  <br/> |<span data-ttu-id="f963f-151">包含用來執行前端伺服器和標準版伺服器的服務帳戶。</span><span class="sxs-lookup"><span data-stu-id="f963f-151">Includes service accounts used to run Front End Server and Standard Edition servers.</span></span> <span data-ttu-id="f963f-152">這個群組可讓伺服器讀/寫商務用 Skype Server 全域設定和 Active Directory 使用者物件的存取權。</span><span class="sxs-lookup"><span data-stu-id="f963f-152">This group allows servers read/write access to Skype for Business Server global settings and Active Directory user objects.</span></span>  <br/> |
|<span data-ttu-id="f963f-153">RTCComponentUniversalServices</span><span class="sxs-lookup"><span data-stu-id="f963f-153">RTCComponentUniversalServices</span></span>  <br/> |<span data-ttu-id="f963f-154">包含用來執行 A/V 會議伺服器、Web 服務、中繼伺服器、封存伺服器及監視伺服器的服務帳戶。</span><span class="sxs-lookup"><span data-stu-id="f963f-154">Includes service accounts used to run A/V Conferencing Servers, Web Services, Mediation Server, Archiving Server, and Monitoring Server.</span></span>  <br/> |
|<span data-ttu-id="f963f-155">RTCProxyUniversalServices</span><span class="sxs-lookup"><span data-stu-id="f963f-155">RTCProxyUniversalServices</span></span>  <br/> |<span data-ttu-id="f963f-156">包含用來執行商務用 Skype Server Edge 伺服器的服務帳戶。</span><span class="sxs-lookup"><span data-stu-id="f963f-156">Includes service accounts used to run Skype for Business Server Edge Servers.</span></span>  <br/> |
|<span data-ttu-id="f963f-157">RTCUniversalConfigReplicator</span><span class="sxs-lookup"><span data-stu-id="f963f-157">RTCUniversalConfigReplicator</span></span>  <br/> |<span data-ttu-id="f963f-158">包括可參與商務用 Skype Server 中央管理儲存複製的伺服器。</span><span class="sxs-lookup"><span data-stu-id="f963f-158">Includes servers that can participate in Skype for Business Server Central Management store replication.</span></span>  <br/> |
|<span data-ttu-id="f963f-159">RTCSBAUniversalServices</span><span class="sxs-lookup"><span data-stu-id="f963f-159">RTCSBAUniversalServices</span></span>  <br/> |<span data-ttu-id="f963f-160">授與商務用 Skype Server 設定的唯讀存取權, 但允許安裝 survivable 分支伺服器和 survivable 分支裝置部署。</span><span class="sxs-lookup"><span data-stu-id="f963f-160">Grants read-only access to Skype for Business Server settings, but allows for configuration for the installation of a survivable branch server and survivable branch appliance deployment.</span></span>  <br/> |

<span data-ttu-id="f963f-161">[林準備] 接著會將服務和系統管理群組新增至適當的基礎結構群組, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="f963f-161">Forest preparation then adds service and administration groups to the appropriate infrastructure groups, as follows:</span></span>

- <span data-ttu-id="f963f-162">RTCUniversalServerAdmins 已新增至 RTCUniversalGlobalReadOnlyGroup、RTCUniversalGlobalWriteGroup、RTCUniversalServerReadOnlyGroup 和 RTCUniversalUserReadOnlyGroup。</span><span class="sxs-lookup"><span data-stu-id="f963f-162">RTCUniversalServerAdmins is added to RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

- <span data-ttu-id="f963f-163">RTCUniversalUserAdmins 會新增為 RTCUniversalGlobalReadOnlyGroup、RTCUniversalServerReadOnlyGroup 和 RTCUniversalUserReadOnlyGroup 的成員。</span><span class="sxs-lookup"><span data-stu-id="f963f-163">RTCUniversalUserAdmins is added as a member of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

- <span data-ttu-id="f963f-164">RTCHSUniversalServices、RTCComponentUniversalServices 和 RTCUniversalReadOnlyAdmins 會新增為 RTCUniversalGlobalReadOnlyGroup、RTCUniversalServerReadOnlyGroup 和 RTCUniversalUserReadOnlyGroup 的成員。</span><span class="sxs-lookup"><span data-stu-id="f963f-164">RTCHSUniversalServices, RTCComponentUniversalServices and RTCUniversalReadOnlyAdmins are added as members of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

<span data-ttu-id="f963f-165">林準備也會建立下列角色式存取控制 (RBAC) 群組:</span><span class="sxs-lookup"><span data-stu-id="f963f-165">Forest preparation also creates the following role-based access control (RBAC) groups:</span></span>

- <span data-ttu-id="f963f-166">CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="f963f-166">CSAdministrator</span></span>

- <span data-ttu-id="f963f-167">CSArchivingAdministrator</span><span class="sxs-lookup"><span data-stu-id="f963f-167">CSArchivingAdministrator</span></span>

- <span data-ttu-id="f963f-168">CSHelpDesk</span><span class="sxs-lookup"><span data-stu-id="f963f-168">CSHelpDesk</span></span>

- <span data-ttu-id="f963f-169">CSLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="f963f-169">CSLocationAdministrator</span></span>

- <span data-ttu-id="f963f-170">CSResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="f963f-170">CSResponseGroupAdministrator</span></span>

- <span data-ttu-id="f963f-171">CSServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="f963f-171">CSServerAdministrator</span></span>

- <span data-ttu-id="f963f-172">CSUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="f963f-172">CSUserAdministrator</span></span>

- <span data-ttu-id="f963f-173">CSViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="f963f-173">CSViewOnlyAdministrator</span></span>

- <span data-ttu-id="f963f-174">CSVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="f963f-174">CSVoiceAdministrator</span></span>

- <span data-ttu-id="f963f-175">CsPersistentChatAdministator</span><span class="sxs-lookup"><span data-stu-id="f963f-175">CsPersistentChatAdministator</span></span>

- <span data-ttu-id="f963f-176">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="f963f-176">CsResponseGroupManager</span></span>

<span data-ttu-id="f963f-177">如需 RBAC 角色及每個角色所允許的工作的詳細資訊, 請參閱規劃檔中的[角色式存取控制](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx)。</span><span class="sxs-lookup"><span data-stu-id="f963f-177">For details about RBAC roles and the tasks allowed for each, see [Role-Based Access Control](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) in the Planning documentation.</span></span>

<span data-ttu-id="f963f-178">林準備會建立私人和公用 Ace。</span><span class="sxs-lookup"><span data-stu-id="f963f-178">Forest preparation creates both private and public ACEs.</span></span> <span data-ttu-id="f963f-179">它會在商務用 Skype Server 所使用的全域設定容器上建立私用 Ace。</span><span class="sxs-lookup"><span data-stu-id="f963f-179">It creates private ACEs on the global settings container used by Skype for Business Server.</span></span> <span data-ttu-id="f963f-180">這個容器只能由商務用 Skype Server 使用, 且位於配置容器或根網域中的系統容器中, 視您儲存全域設定的位置而定。</span><span class="sxs-lookup"><span data-stu-id="f963f-180">This container is used only by Skype for Business Server and is located either in the Configuration container or the System container in the root domain, depending on where you store global settings.</span></span> <span data-ttu-id="f963f-181">[林準備] 建立的公用 Ace 列在下表中。</span><span class="sxs-lookup"><span data-stu-id="f963f-181">The public ACEs created by forest preparation are listed in the following table.</span></span>

<span data-ttu-id="f963f-182">**由林準備建立的公用 Ace**</span><span class="sxs-lookup"><span data-stu-id="f963f-182">**Public ACEs created by Forest Preparation**</span></span>


| <span data-ttu-id="f963f-183">**A**</span><span class="sxs-lookup"><span data-stu-id="f963f-183">**ACE**</span></span>                                                                 | <span data-ttu-id="f963f-184">**RTCUniversalGlobalReadOnlyGroup**</span><span class="sxs-lookup"><span data-stu-id="f963f-184">**RTCUniversalGlobalReadOnlyGroup**</span></span> |
|:------------------------------------------------------------------------|:------------------------------------|
| <span data-ttu-id="f963f-185">讀取根網域系統容器 (不繼承)**\\**\*</span><span class="sxs-lookup"><span data-stu-id="f963f-185">Read root domain System Container (not inherited) **\\**\*</span></span> <br/>        | <span data-ttu-id="f963f-186">X</span><span class="sxs-lookup"><span data-stu-id="f963f-186">X</span></span>  <br/>                            |
| <span data-ttu-id="f963f-187">讀取配置的 DisplaySpecifiers 容器 (不是繼承的)</span><span class="sxs-lookup"><span data-stu-id="f963f-187">Read Configuration's DisplaySpecifiers container (not inherited)</span></span>  <br/> | <span data-ttu-id="f963f-188">X</span><span class="sxs-lookup"><span data-stu-id="f963f-188">X</span></span>  <br/>                            |

> [!NOTE]
> <span data-ttu-id="f963f-189"><strong>\\</strong>\* 沒有繼承的 Ace 不會在這些容器下授與子物件的存取權。</span><span class="sxs-lookup"><span data-stu-id="f963f-189"><strong>\\</strong>\*ACEs that are not inherited do not grant access to child objects under these containers.</span></span> <span data-ttu-id="f963f-190">被繼承的 Ace 在這些容器下授與子物件的存取權。</span><span class="sxs-lookup"><span data-stu-id="f963f-190">ACEs that are inherited grant access to child objects under these containers.</span></span>

<span data-ttu-id="f963f-191">在 [設定] 容器的 [設定命名] 內容底下, [林準備] 會執行下列任務:</span><span class="sxs-lookup"><span data-stu-id="f963f-191">On the Configuration container, under the Configuration naming context, forest preparation performs the following tasks:</span></span>

- <span data-ttu-id="f963f-192">針對使用者、連絡人和 InetOrgPersons (例如 CN = AB255F23-2DBD-4bb6-891D-38754AC280EF) 的語言顯示說明符之 [adminCoNtextMenu] 和 [adminPropertyPages] 屬性, 在 [ **RTC] 屬性**頁面上新增專案 **{}** 使用者顯示, CN = 409, CN = DisplaySpecifiers)。</span><span class="sxs-lookup"><span data-stu-id="f963f-192">Adds an entry **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** for the **RTC property** page under the adminContextMenu and adminPropertyPages attributes of the language display specifier for users, contacts, and InetOrgPersons (for example, CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>

- <span data-ttu-id="f963f-193">在套用至使用者和連絡人類別的**延伸許可權**底下, 新增類型**controlAccessRight**的**RTCPropertySet**物件。</span><span class="sxs-lookup"><span data-stu-id="f963f-193">Adds an **RTCPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to the User and Contact classes.</span></span>

- <span data-ttu-id="f963f-194">在適用于使用者、連絡人、OU 和 DomainDNS 類別的**延伸許可權**底下, 新增類型**controlAccessRight**的**RTCUserSearchPropertySet**物件。</span><span class="sxs-lookup"><span data-stu-id="f963f-194">Adds an **RTCUserSearchPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to User, Contact, OU, and DomainDNS classes.</span></span>

- <span data-ttu-id="f963f-195">在每個語言組織單位 (OU) 顯示說明符的**extraColumns**屬性 (例如, Cn = OrganizationalUnit-DISPLAY、cn = 409、Cn = DisplaySpecifiers) 下新增**msRTCSIP-PrimaryUserAddress** , 並將其值複製預設顯示的**extraColumns**屬性 (例如, cn = 預設顯示, cn = 409, Cn = DisplaySpecifiers)。</span><span class="sxs-lookup"><span data-stu-id="f963f-195">Adds **msRTCSIP-PrimaryUserAddress** under the **extraColumns** attribute of each language organizational unit (OU) display specifier (for example, CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers) and copies the values of the **extraColumns** attribute of the default display (for example, CN=default-Display, CN=409,CN=DisplaySpecifiers).</span></span>

- <span data-ttu-id="f963f-196">將**msRTCSIP-PrimaryUserAddress**、 **msRTCSIP-PrimaryHomeServer**及**msRTCSIP-UserEnabled**篩選屬性新增至每個語言顯示指定符的**AttributeDisplayNames**屬性, 以供使用者、連絡人、InetOrgPerson 物件 (例如英文): CN = 使用者顯示, CN = 409, CN = DisplaySpecifiers)。</span><span class="sxs-lookup"><span data-stu-id="f963f-196">Adds **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer**, and **msRTCSIP-UserEnabled** filtering attributes under the **attributeDisplayNames** attribute of each language display specifier for Users, Contacts, and InetOrgPerson objects (for example, in English: CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>


