```json
{
      "id": "gen_7f17b555",
      "description": {
        "purpose": "Test resolution path: No Service/Connection Issues.",
        "relevant_policies": "Telecom Agent Policy, Phone Device - Technical Support Troubleshooting Workflow",
        "notes": "Testing path 1.1, 1.2, and 1.3 in the troubleshooting workflow."
      },
      "user_scenario": {
        "persona": "Alice is a 29-year-old freelance digital artist. She relies heavily on her smartphone for coordination with clients and social media updates. While she is generally comfortable with technology, she has a low tolerance for downtime and becomes increasingly anxious when she can't access her messages or calls. She tends to be brief in her responses and expects quick solutions.",
        "instructions": {
          "domain": "telecom",
          "reason_for_call": "Your phone has been showing 'No Service' for the last few hours, and you are unable to make any calls or use the internet. You need this fixed immediately.",
          "known_info": "You are Alice C1901E3C with phone number 506-443-5550.",
          "unknown_info": null,
          "task_instructions": "You will consider the issue resolved only when the status bar indicates that you have service. Follow the agent's instructions, but if the first fix (Airplane Mode) doesn't work, express that you are frustrated because you have a deadline. Always perform the tools the agent asks you to and report the results exactly as shown in the tool outputs. You must check the status bar or network status whenever the agent asks for the current state of your phone. If they ask to reset settings or reboot, do so and then check the status again."
        }
      },
      "ticket": "The user Alice Cooper (506-443-5550) is reporting 'No Service' on her device. She cannot place calls or access data. The issue started a few hours ago. Technical support Path 1 is required.",
      "initial_state": {
        "initialization_data": null,
        "initialization_actions": [
          {
            "env_type": "user",
            "func_name": "set_user_info",
            "arguments": {
              "name": "Alice Cooper",
              "phone_number": "506-443-5550"
            }
          },
          {
            "env_type": "user",
            "func_name": "turn_airplane_mode_on",
            "arguments": {}
          },
          {
            "env_type": "user",
            "func_name": "unseat_sim_card",
            "arguments": {}
          },
          {
            "env_type": "user",
            "func_name": "break_apn_settings",
            "arguments": {}
          },
          {
            "env_type": "user",
            "func_name": "simulate_network_search",
            "arguments": {}
          }
        ],
        "message_history": null
      },
      "evaluation_criteria": {
        "actions": [
          {
            "action_id": "toggle_airplane_mode_0",
            "requestor": "user",
            "name": "toggle_airplane_mode",
            "arguments": {},
            "info": null,
            "compare_args": null
          },
          {
            "action_id": "reseat_sim_card_1",
            "requestor": "user",
            "name": "reseat_sim_card",
            "arguments": {},
            "info": null,
            "compare_args": null
          },
          {
            "action_id": "reset_apn_settings_2",
            "requestor": "user",
            "name": "reset_apn_settings",
            "arguments": {},
            "info": null,
            "compare_args": null
          },
          {
            "action_id": "reboot_device_3",
            "requestor": "user",
            "name": "reboot_device",
            "arguments": {},
            "info": null,
            "compare_args": null
          }
        ],
        "env_assertions": [
          {
            "env_type": "user",
            "func_name": "assert_service_status",
            "arguments": {
              "expected_status": "connected"
            },
            "assert_value": true,
            "message": "Service status should be connected after all troubleshooting steps."
          }
        ],
        "communicate_info": [
          "The signal has been restored.",
          "Service is now active."
        ],
        "nl_assertions": [
          "The agent successfully guided the user through Airplane Mode, SIM reseating, and APN reset."
        ],
        "reward_basis": [
          "ENV_ASSERTION",
          "ACTION"
        ]
      }
}
```

```toml
[[customers]]
customer_id = "C1901E3C"
full_name = "Alice Cooper"
date_of_birth = "1996-04-12"
email = "a.cooper.design@example.com"
phone_number = "506-443-5550"
account_status = "Active"
created_at = "2023-11-01T09:00:00"
goodwill_credit_used_this_year = 0.0
line_ids = ["LD00B14F"]
bill_ids = ["B00AC822"]

[[customers.payment_methods]]
method_type = "Debit Card"
account_number_last_4 = "9988"
expiration_date = "05/2027"

[customers.address]
street = "742 Evergreen Terrace"
city = "Springfield"
state = "IL"
zip_code = "62704"

[[bills]]
bill_id = "B00AC822"
customer_id = "C1901E3C"
period_start = "2025-01-01"
period_end = "2025-01-31"
issue_date = "2025-02-01"
total_due = 55.0
due_date = "2025-02-15"
status = "Paid"

[[bills.line_items]]
description = "Standard Monthly Plan"
amount = 55.0
date = "2025-02-01"
item_type = "Plan Charge"

[[lines]]
line_id = "LD00B14F"
phone_number = "506-443-5550"
status = "Active"
plan_id = "PFE0A65B"
device_id = "D49F1F6A"
data_used_gb = 4.2
data_refueling_gb = 0.0
roaming_enabled = true
contract_end_date = "2025-11-01"
last_plan_change_date = "2023-11-01"
last_sim_replacement_date = "2023-11-01"

[[plans]]
plan_id = "PFE0A65B"
name = "Standard Creative Plan"
data_limit_gb = 20.0
price_per_month = 55.0
data_refueling_price_per_gb = 5.0

[[devices]]
device_id = "D49F1F6A"
device_type = "phone"
model = "iFrame 15 Pro"
imei = "990000123456789"
is_esim_capable = true
activated = true
activation_date = "2023-11-01T10:00:00"
```

<details markdown="block">

<summary>Task (Click to show/hide)</summary>


```json
{
      "id": "gen_7f17b555",
      "description": {
        "purpose": "Test resolution path: No Service/Connection Issues.",
        "relevant_policies": "Telecom Agent Policy, Phone Device - Technical Support Troubleshooting Workflow",
        "notes": "Testing path 1.1, 1.2, and 1.3 in the troubleshooting workflow."
      },
      "user_scenario": {
        "persona": "Alice is a 29-year-old freelance digital artist. She relies heavily on her smartphone for coordination with clients and social media updates. While she is generally comfortable with technology, she has a low tolerance for downtime and becomes increasingly anxious when she can't access her messages or calls. She tends to be brief in her responses and expects quick solutions.",
        "instructions": {
          "domain": "telecom",
          "reason_for_call": "Your phone has been showing 'No Service' for the last few hours, and you are unable to make any calls or use the internet. You need this fixed immediately.",
          "known_info": "You are Alice C1901E3C with phone number 506-443-5550.",
          "unknown_info": null,
          "task_instructions": "You will consider the issue resolved only when the status bar indicates that you have service. Follow the agent's instructions, but if the first fix (Airplane Mode) doesn't work, express that you are frustrated because you have a deadline. Always perform the tools the agent asks you to and report the results exactly as shown in the tool outputs. You must check the status bar or network status whenever the agent asks for the current state of your phone. If they ask to reset settings or reboot, do so and then check the status again."
        }
      },
      "ticket": "The user Alice Cooper (506-443-5550) is reporting 'No Service' on her device. She cannot place calls or access data. The issue started a few hours ago. Technical support Path 1 is required.",
      "initial_state": {
        "initialization_data": null,
        "initialization_actions": [
          {
            "env_type": "user",
            "func_name": "set_user_info",
            "arguments": {
              "name": "Alice Cooper",
              "phone_number": "506-443-5550"
            }
          },
          {
            "env_type": "user",
            "func_name": "turn_airplane_mode_on",
            "arguments": {}
          },
          {
            "env_type": "user",
            "func_name": "unseat_sim_card",
            "arguments": {}
          },
          {
            "env_type": "user",
            "func_name": "break_apn_settings",
            "arguments": {}
          },
          {
            "env_type": "user",
            "func_name": "simulate_network_search",
            "arguments": {}
          }
        ],
        "message_history": null
      },
      "evaluation_criteria": {
        "actions": [
          {
            "action_id": "toggle_airplane_mode_0",
            "requestor": "user",
            "name": "toggle_airplane_mode",
            "arguments": {},
            "info": null,
            "compare_args": null
          },
          {
            "action_id": "reseat_sim_card_1",
            "requestor": "user",
            "name": "reseat_sim_card",
            "arguments": {},
            "info": null,
            "compare_args": null
          },
          {
            "action_id": "reset_apn_settings_2",
            "requestor": "user",
            "name": "reset_apn_settings",
            "arguments": {},
            "info": null,
            "compare_args": null
          },
          {
            "action_id": "reboot_device_3",
            "requestor": "user",
            "name": "reboot_device",
            "arguments": {},
            "info": null,
            "compare_args": null
          }
        ],
        "env_assertions": [
          {
            "env_type": "user",
            "func_name": "assert_service_status",
            "arguments": {
              "expected_status": "connected"
            },
            "assert_value": true,
            "message": "Service status should be connected after all troubleshooting steps."
          }
        ],
        "communicate_info": [
          "The signal has been restored.",
          "Service is now active."
        ],
        "nl_assertions": [
          "The agent successfully guided the user through Airplane Mode, SIM reseating, and APN reset."
        ],
        "reward_basis": [
          "ENV_ASSERTION",
          "ACTION"
        ]
      }
}
```

</details>

