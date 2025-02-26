<template>
    <div class="brandText my-3 py-3">
        <div class="container">
            <h1 class="text-center text-capitalize">Simple CRM. Simpler Pricing.</h1>
            <small>Bigin's promise to you is simple: No forced multi-year contracts, no hidden charges. You don't need
                to enter your credit card information to get started. Cancel anytime!</small>

            <div class="my-3">
                <ul class="nav nav-pills justify-content-center sticky-container bg-dark" id="pills-tab" role="tablist">
                    <div class="d-flex p-2 px-3 rounded" style="">
                        <li class="nav-item" role="presentation" v-for="(price, index) in pricing" :key="index">
                            <button class="nav-link text-white" :class="{ 'active': index === 0 }" :id="'tab-' + index"
                                data-bs-toggle="pill" :data-bs-target="'#content-' + index" type="button" role="tab"
                                :aria-controls="'content-' + index" :aria-selected="index === 0">{{ price.name
                                }}</button>
                        </li>
                    </div>
                </ul>
                <div class="tab-content mt-2 pt-4" id="pills-tabContent">
                    <div class="tab-pane fade" :class="{ 'show active': index === 0 }" v-for="(price, index) in pricing"
                        :key="index" :id="'content-' + index" role="tabpanel" :aria-labelledby="'tab-' + index"
                        tabindex="0">
                        <div class="d-md-flex justify-content-center gap-3">
                            <div v-for="(plan, index) in price.plans" :key="index"
                                class="card mb-3 px-3 bg-dark text-white rounded-0" :class="{ 'recommended': index === 1 }">

                                <div v-if="index === 1" class="position-absolute top-0 start-0 m-2 ms-0"
                                    style="font-size: 12px;">
                                    <span class='text-white bg-danger p-1 px-2 rounded-end-3'>Recommended</span>
                                </div>

                                <div class="py-2 border-bottom fw-bold">{{
                                    plan.name }}</div>
                                <div class="card-body text-center">
                                    <p class="mb-0 card-title fs-3">₹ <span class="fw-bold">{{ plan.price }} </span></p>
                                    <p><small class="text-capitalize">{{ plan.tag
                                            }}</small></p>
                                    <div class="d-flex justify-content-center align-items-center">
                                        <p class="fw-light bg-dark  d-inline-block px-4 rounded-3">
                                            <span class="text-decoration-line-through text-white">{{ plan.mrp }}</span>
                                            <!-- <span class="text-white"> ({{ getDiscount(plan) }}% discount)</span> -->
                                        </p>
                                    </div>

                                    <ul v-if="plan.features" class="list-group">
                                        <small class="text-start text-uppercase fw-bold my-2 text-primary">{{ plan.key
                                            }}</small>
                                        <li v-for="(feature, featureIndex) in plan.features" :key="featureIndex"
                                            class="bg-dark text-white px-0 d-flex justify-content-between list-group-item text-start text-capitalize border-0">
                                            <div class="">
                                                <i class="bi bi-check-circle text-success"></i>
                                                <span class="px-2">
                                                    {{ feature.text }}
                                                </span>
                                            </div>
                                            <i class="bi bi-info-circle" data-bs-toggle="tooltip"
                                                data-bs-placement="top" data-bs-custom-class="custom-tooltip"
                                                :data-bs-title="feature.tooltip"></i>
                                        </li>
                                    </ul>
                                </div>
                                <div class="card-footer bg-dark p-0 border-top pt-2">
                                    <p class="card-text text-capitalize">{{ plan.description }}</p>
                                    <div class="d-flex justify-content-center gap-2 my-3">
                                        <button class="btn btn-danger w-100">{{ plan.button }}</button>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                 
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "PriceSection",
    data() {
        return {
            pricing: [
                {
                    id: 2,
                    name: "Yearly",
                    description: "This is a basic plan",
                    plans: [
                        {
                            id: 1,
                            name: "Starter",
                            price: "500",
                            mrp: "5,000",
                            tag: "/user/yearly/billed yearly",
                            description: "Start with our free plan and upgrade only when you need additional features.",
                            button: "Get Started",
                            key: "key features",
                            features: [
                                {
                                    text: "single Pipelines",
                                    tooltip: "get a quick summary fo your customer-facing process and manage opportunities across different stages."
                                },
                                {
                                    text: "500 Records",
                                    tooltip: "Each row of data you enter in pipelines, contacts, companies, activities and notes are called records in saleswik."
                                },
                                {
                                    text: "Automations (3)",
                                    tooltip: "Automate repetitive actions by setting up triggers and specifying the conditions to be met for the execution of the actions."
                                },
                                {
                                    text: "telephony",
                                    tooltip: "Make and receive phone calls, record them , set up automated voice responses, and use call routing--dicrectly in saleswik."
                                },
                                {
                                    text: "zapier, SalesWik desk , SalesWik campaigns, and SalesWik forms integration",
                                    tooltip: "Seamless integrate saleswik with other third party apps."
                                },
                                {
                                    text: "apps for IOS, iPadOS, android and macOS",
                                    tooltip: "Enjoy a fully featured saleswik app for mobile devices that enables yout to do everthing you can do on your desktop while on the go."
                                },
                                {
                                    text: "developer APIs",
                                    tooltip: "Highly secure developer APIs that help you contact saleswik to any third-party app of your choice"
                                },
                                {
                                    text: "standard dashboard",
                                    tooltip: "Monitor your business performance with charts and KPIs. Create your own dashboards and keep them privae or share them with everyone else."
                                }
                            ]
                        },
                        {
                            id: 2,
                            name: "Professional",
                            price: "1000",
                            mrp: "10,000",
                            tag: "/user/yearly/billed yearly",
                            description: "Choose the right set of features you need to begin your CRM journey.",
                            button: "Get Started",
                            button2: "Buy now",
                            key: "key features",
                            features: [
                                {
                                    text: "Team Pipelines (3)",
                                    tooltip: "Create distinct pipelines for every team and unify all your customer-facing operations."
                                },
                                {
                                    text: "500000 Records",
                                    tooltip: "Each row of data you enter in pipelines, contacts, companies, activities adn notes are called records in saleswik. You can purchase additional records if you need to store more than 50000 records."
                                },
                                {
                                    text: "Automations (30)",
                                    tooltip: "Automate a wider range of instant actions to further reduce the time, effort, and errors that go into doing mundane tasks."
                                },
                                {
                                    text: "Email & WhatsApp Business Integration",
                                    tooltip: "Connect all major services to your saleswik account with IMAP, send mass emails, and get email open/click notifications."
                                },
                                {
                                    text: "Mass emails with email insights",
                                    tooltip: "Send emails to multiple customers with a single click and use insights to capture the exact status of each email."
                                },
                                {
                                    text: "No-code forms for contact & pipelines",
                                    tooltip: "Deploy saleswik webforms on your website easily to  collect information from your website visitors."
                                },
                                {
                                    text: "10 custom fields/module",
                                    tooltip: "Create custom fields that suit your business needs."
                                },
                                {
                                    text: "Customizable dashboards with charts and KPIs",
                                    tooltip: "Customize your dashboards according to your needs and analyze your business performance with carts and KPIs."
                                },
                                {
                                    text: "Integrate with SalesWik Books/Invoice, SalesWik CRM and SalesWik Meeting",
                                    tooltip: "Seamlessly integrate saleswik with other third party apps."
                                },
                                {
                                    text: "Integrate with Google Workspace, Microsoft 365, Zoom Meeting, Mailchimp, and Twitter",
                                    tooltip: "Easily integrate with saleswik apps and other third-party apps."
                                },
                                {
                                    text: "Additional capabilities via toppings",
                                    tooltip: "SalesWik offers topping like file cabinet and email in to enhance your CRM usage."
                                }
                            ]
                        },
                        {
                            id: 3,
                            name: "Enterprise",
                            price: "5,000",
                            mrp: "50,000",
                            tag: "/user/yearly/billed yearly",
                            description: "Enjoy our advanced offering for fast-growing businesses and startups.",
                            button: "Get Started",
                            button2: "Buy now",
                            key: "key features",
                            features: [
                                {
                                    text: "Team Pipelines",
                                    tooltip: "Get aquick summary of every customer-facing operation by creating distinct pipelines for each team."
                                },
                                {
                                    text: "100000 Records",
                                    tooltip: "Each row of data you enter in pieplines, contacts, companies, activities and notes are called records in saleswik. You can purchase additional records if you need to store more than 100000 records."
                                },
                                {
                                    text: "Advanced automation (50)",
                                    tooltip: "Schedule workflows that are triggered at specified time intervals."
                                },
                                {
                                    text: "Stage transition rules",
                                    tooltip: "Set up rules for moving deals in your pipelines, create checkpoints to enxure deals properly transition between stages."
                                },
                                {
                                    text: "Sell globally with multiple currencies",
                                    tooltip: "Run operations in more than just your local currency. SalesWik takes care of all exchange rates and conversions."
                                },
                                {
                                    text: "Additional field type: lookup, user fields",
                                    tooltip: "Create new fields and establish connections between records within different modules for your own context."
                                },
                                {
                                    text: "25 custom fields per module",
                                    tooltip: "Create custom fields that suit your business needs."
                                },
                                {
                                    text: "Cleanup duplicates",
                                    tooltip: "Manage and clean up duplicate records in your CRM more effectively."
                                },
                                {
                                    text: "Target meter - dashboards",
                                    tooltip: "Set and monitor important targets for your sales and customer-facing teams."
                                },
                                {
                                    text: "Increased feature limits",
                                    tooltip: "Enjoy the highest possible feature limits on key SalesWik features."
                                }
                            ]
                        }
                    ]
                },
                {
                    id: 3,
                    name: "Quartly",
                    description: "This is a basic plan",
                    plans: [
                        {
                            id: 1,
                            name: "Starter",
                            price: "1,250",
                            mrp: "5,000",
                            tag: "/user/quartly/billed quartly",
                            description: "Start with our free plan and upgrade only when you need additional features.",
                            button: "Get Started",
                            key: "key features",
                            features: [
                                {
                                    text: "single Pipelines",
                                    tooltip: "get a quick summary fo your customer-facing process and manage opportunities across different stages."
                                },
                                {
                                    text: "500 Records",
                                    tooltip: "Each row of data you enter in pipelines, contacts, companies, activities and notes are called records in saleswik."
                                },
                                {
                                    text: "Automations (3)",
                                    tooltip: "Automate repetitive actions by setting up triggers and specifying the conditions to be met for the execution of the actions."
                                },
                                {
                                    text: "telephony",
                                    tooltip: "Make and receive phone calls, record them , set up automated voice responses, and use call routing--dicrectly in saleswik."
                                },
                                {
                                    text: "zapier, SalesWik desk , SalesWik campaigns, and SalesWik forms integration",
                                    tooltip: "Seamless integrate saleswik with other third party apps."
                                },
                                {
                                    text: "apps for IOS, iPadOS, android and macOS",
                                    tooltip: "Enjoy a fully featured saleswik app for mobile devices that enables yout to do everthing you can do on your desktop while on the go."
                                },
                                {
                                    text: "developer APIs",
                                    tooltip: "Highly secure developer APIs that help you contact saleswik to any third-party app of your choice"
                                },
                                {
                                    text: "standard dashboard",
                                    tooltip: "Monitor your business performance with charts and KPIs. Create your own dashboards and keep them privae or share them with everyone else."
                                }
                            ]
                        },
                        {
                            id: 2,
                            name: "Professional",
                            price: "2,500",
                            mrp: "10,000",
                            tag: "/user/quartly/billed quartly",
                            description: "Choose the right set of features you need to begin your CRM journey.",
                            button: "Get Started",
                            button2: "Buy now",
                            key: "key features",
                            features: [
                                {
                                    text: "Team Pipelines (3)",
                                    tooltip: "Create distinct pipelines for every team and unify all your customer-facing operations."
                                },
                                {
                                    text: "500000 Records",
                                    tooltip: "Each row of data you enter in pipelines, contacts, companies, activities adn notes are called records in saleswik. You can purchase additional records if you need to store more than 50000 records."
                                },
                                {
                                    text: "Automations (30)",
                                    tooltip: "Automate a wider range of instant actions to further reduce the time, effort, and errors that go into doing mundane tasks."
                                },
                                {
                                    text: "Email & WhatsApp Business Integration",
                                    tooltip: "Connect all major services to your saleswik account with IMAP, send mass emails, and get email open/click notifications."
                                },
                                {
                                    text: "Mass emails with email insights",
                                    tooltip: "Send emails to multiple customers with a single click and use insights to capture the exact status of each email."
                                },
                                {
                                    text: "No-code forms for contact & pipelines",
                                    tooltip: "Deploy saleswik webforms on your website easily to  collect information from your website visitors."
                                },
                                {
                                    text: "10 custom fields/module",
                                    tooltip: "Create custom fields that suit your business needs."
                                },
                                {
                                    text: "Customizable dashboards with charts and KPIs",
                                    tooltip: "Customize your dashboards according to your needs and analyze your business performance with carts and KPIs."
                                },
                                {
                                    text: "Integrate with SalesWik Books/Invoice, SalesWik CRM and SalesWik Meeting",
                                    tooltip: "Seamlessly integrate saleswik with other third party apps."
                                },
                                {
                                    text: "Integrate with Google Workspace, Microsoft 365, Zoom Meeting, Mailchimp, and Twitter",
                                    tooltip: "Easily integrate with saleswik apps and other third-party apps."
                                },
                                {
                                    text: "Additional capabilities via toppings",
                                    tooltip: "SalesWik offers topping like file cabinet and email in to enhance your CRM usage."
                                }
                            ]
                        },
                        {
                            id: 3,
                            name: "Enterprise",
                            price: "12,500",
                            mrp: "50,000",
                            tag: "/user/quartly/billed quartly",
                            description: "Enjoy our advanced offering for fast-growing businesses and startups.",
                            button: "Get Started",
                            button2: "Buy now",
                            key: "key features",
                            features: [
                                {
                                    text: "Team Pipelines",
                                    tooltip: "Get aquick summary of every customer-facing operation by creating distinct pipelines for each team."
                                },
                                {
                                    text: "100000 Records",
                                    tooltip: "Each row of data you enter in pieplines, contacts, companies, activities and notes are called records in saleswik. You can purchase additional records if you need to store more than 100000 records."
                                },
                                {
                                    text: "Advanced automation (50)",
                                    tooltip: "Schedule workflows that are triggered at specified time intervals."
                                },
                                {
                                    text: "Stage transition rules",
                                    tooltip: "Set up rules for moving deals in your pipelines, create checkpoints to enxure deals properly transition between stages."
                                },
                                {
                                    text: "Sell globally with multiple currencies",
                                    tooltip: "Run operations in more than just your local currency. SalesWik takes care of all exchange rates and conversions."
                                },
                                {
                                    text: "Additional field type: lookup, user fields",
                                    tooltip: "Create new fields and establish connections between records within different modules for your own context."
                                },
                                {
                                    text: "25 custom fields per module",
                                    tooltip: "Create custom fields that suit your business needs."
                                },
                                {
                                    text: "Cleanup duplicates",
                                    tooltip: "Manage and clean up duplicate records in your CRM more effectively."
                                },
                                {
                                    text: "Target meter - dashboards",
                                    tooltip: "Set and monitor important targets for your sales and customer-facing teams."
                                },
                                {
                                    text: "Increased feature limits",
                                    tooltip: "Enjoy the highest possible feature limits on key SalesWik features."
                                }
                            ]
                        }
                    ]
                },
                {
                    id: 1,
                    name: "Monthly",
                    description: "This is a basic plan",
                    plans: [
                        {
                            id: 1,
                            name: "Starter",
                            price: "2,500",
                            mrp: "5,000",
                            tag: "/user/month/billed monthly",
                            description: "Start with our free plan and upgrade only when you need additional features.",
                            button: "Get Started",
                            key: "key features",
                            features: [
                                {
                                    text: "single Pipelines",
                                    tooltip: "get a quick summary fo your customer-facing process and manage opportunities across different stages."
                                },
                                {
                                    text: "500 Records",
                                    tooltip: "Each row of data you enter in pipelines, contacts, companies, activities and notes are called records in saleswik."
                                },
                                {
                                    text: "Automations (3)",
                                    tooltip: "Automate repetitive actions by setting up triggers and specifying the conditions to be met for the execution of the actions."
                                },
                                {
                                    text: "telephony",
                                    tooltip: "Make and receive phone calls, record them , set up automated voice responses, and use call routing--dicrectly in saleswik."
                                },
                                {
                                    text: "zapier, SalesWik desk , SalesWik campaigns, and SalesWik forms integration",
                                    tooltip: "Seamless integrate saleswik with other third party apps."
                                },
                                {
                                    text: "apps for IOS, iPadOS, android and macOS",
                                    tooltip: "Enjoy a fully featured saleswik app for mobile devices that enables yout to do everthing you can do on your desktop while on the go."
                                },
                                {
                                    text: "developer APIs",
                                    tooltip: "Highly secure developer APIs that help you contact saleswik to any third-party app of your choice"
                                },
                                {
                                    text: "standard dashboard",
                                    tooltip: "Monitor your business performance with charts and KPIs. Create your own dashboards and keep them privae or share them with everyone else."
                                }
                            ]
                        },
                        {
                            id: 2,
                            name: "Professional",
                            price: "5,000",
                            mrp: "10,000",
                            tag: "/user/month/billed monthly",
                            description: "Choose the right set of features you need to begin your CRM journey.",
                            button: "Get Started",
                            button2: "Buy now",
                            key: "key features",
                            features: [
                                {
                                    text: "Team Pipelines (3)",
                                    tooltip: "Create distinct pipelines for every team and unify all your customer-facing operations."
                                },
                                {
                                    text: "500000 Records",
                                    tooltip: "Each row of data you enter in pipelines, contacts, companies, activities adn notes are called records in saleswik. You can purchase additional records if you need to store more than 50000 records."
                                },
                                {
                                    text: "Automations (30)",
                                    tooltip: "Automate a wider range of instant actions to further reduce the time, effort, and errors that go into doing mundane tasks."
                                },
                                {
                                    text: "Email & WhatsApp Business Integration",
                                    tooltip: "Connect all major services to your saleswik account with IMAP, send mass emails, and get email open/click notifications."
                                },
                                {
                                    text: "Mass emails with email insights",
                                    tooltip: "Send emails to multiple customers with a single click and use insights to capture the exact status of each email."
                                },
                                {
                                    text: "No-code forms for contact & pipelines",
                                    tooltip: "Deploy saleswik webforms on your website easily to  collect information from your website visitors."
                                },
                                {
                                    text: "10 custom fields/module",
                                    tooltip: "Create custom fields that suit your business needs."
                                },
                                {
                                    text: "Customizable dashboards with charts and KPIs",
                                    tooltip: "Customize your dashboards according to your needs and analyze your business performance with carts and KPIs."
                                },
                                {
                                    text: "Integrate with SalesWik Books/Invoice, SalesWik CRM and SalesWik Meeting",
                                    tooltip: "Seamlessly integrate saleswik with other third party apps."
                                },
                                {
                                    text: "Integrate with Google Workspace, Microsoft 365, Zoom Meeting, Mailchimp, and Twitter",
                                    tooltip: "Easily integrate with saleswik apps and other third-party apps."
                                },
                                {
                                    text: "Additional capabilities via toppings",
                                    tooltip: "SalesWik offers topping like file cabinet and email in to enhance your CRM usage."
                                }
                            ]
                        },
                        {
                            id: 3,
                            name: "Enterprise",
                            price: "25,000",
                            mrp: "50,000",
                            tag: "/user/month/billed monthly",
                            description: "Enjoy our advanced offering for fast growing businesses and startups.",
                            button: "Get Started",
                            button2: "Buy now",
                            key: "key features",
                            features: [
                                {
                                    text: "Team Pipelines",
                                    tooltip: "Get aquick summary of every customer-facing operation by creating distinct pipelines for each team."
                                },
                                {
                                    text: "100000 Records",
                                    tooltip: "Each row of data you enter in pieplines, contacts, companies, activities and notes are called records in saleswik. You can purchase additional records if you need to store more than 100000 records."
                                },
                                {
                                    text: "Advanced automation (50)",
                                    tooltip: "Schedule workflows that are triggered at specified time intervals."
                                },
                                {
                                    text: "Stage transition rules",
                                    tooltip: "Set up rules for moving deals in your pipelines, create checkpoints to enxure deals properly transition between stages."
                                },
                                {
                                    text: "Sell globally with multiple currencies",
                                    tooltip: "Run operations in more than just your local currency. SalesWik takes care of all exchange rates and conversions."
                                },
                                {
                                    text: "Additional field type: lookup, user fields",
                                    tooltip: "Create new fields and establish connections between records within different modules for your own context."
                                },
                                {
                                    text: "25 custom fields per module",
                                    tooltip: "Create custom fields that suit your business needs."
                                },
                                {
                                    text: "Cleanup duplicates",
                                    tooltip: "Manage and clean up duplicate records in your CRM more effectively."
                                },
                                {
                                    text: "Target meter - dashboards",
                                    tooltip: "Set and monitor important targets for your sales and customer-facing teams."
                                },
                                {
                                    text: "Increased feature limits",
                                    tooltip: "Enjoy the highest possible feature limits on key SalesWik features."
                                }
                            ]
                        }
                    ]
                },


            ],
            
        };
    },
    mounted() {
        this.initTooltips();
    },
    updated() {
        this.initTooltips();
    },
    methods: {
        initTooltips() {
            // Initialize tooltips (assuming using Bootstrap's tooltip)
            const tooltipTriggerList = [].slice.call(
                document.querySelectorAll('[data-bs-toggle="tooltip"]')
            );
            tooltipTriggerList.forEach(function (tooltipTriggerEl) {
                new window.bootstrap.Tooltip(tooltipTriggerEl);
            });
        },
        getDiscount(plan) {
            if (plan.mrp && typeof plan.mrp === 'string') {
                const mrp = parseFloat(plan.mrp.replace(/[^\d.-]/g, ''));
                const price = parseFloat(plan.price.replace(/[^\d.-]/g, ''));
                if (!isNaN(mrp) && !isNaN(price) && mrp > 0) {
                    return ((mrp - price) / mrp * 100).toFixed(0);
                }
            }
            return 0; // Default return if calculation fails
        }

    }
};
</script>

<style scoped>
.nav-link {
    transition: background-color 0.3s ease, color 0.3s ease;
}

.nav-link.active {
    background-color: var(--bg-primary) !important;
    color: white !important;
    transition: background-color 0.3s ease, color 0.3s ease, transform 0.3s ease;
    transform: scale(1.2);
}

.sticky-container {
    position: sticky;
    top: 70px;
    z-index: 1000;
    background-color: white;
}


/* .recommended {
    border: 4px solid #efc107; 
    position: relative;
}

.recommended::before {
    content: "Recommended";
    position: absolute;
    top: -20px;
    left: -4px;
    width: 102.5%;
    background: #efc107; 
    color: white;
    padding: 5px 10px;
    font-size: 0.9rem;
    font-weight: bold;
    border-radius: 3px;
} */

/* Add any necessary styling here */
</style>
