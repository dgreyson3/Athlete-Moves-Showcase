# Athlete Moves

**A cross-platform workout app connecting athlete assessment, interactive training, and history-informed progression.**

Built independently by **Greyson Denison-Fischer** · **Functional development prototype** · **2026**  
**Platform targets:** iPhone/iPad, Android, and mobile/desktop web

Athlete Moves brings the training workflow into one application: assess an athlete's starting level, discover matched workouts, record a session, and review completed performance. It combines React Native and Expo with Supabase authentication and PostgreSQL-backed workout history.

> **Project case study:** This repository documents the application and my engineering contribution. Application source code and private implementation details are not included.

<!-- PRODUCT_GALLERY -->

## What I built

I independently implemented the mobile interface and responsive design system, account and assessment flows, workout discovery, active workout tracking, timers, history, recommendation and level-progression logic, and Supabase integration and data setup.

| Part of the experience | Implemented behavior |
| --- | --- |
| **Account and assessment** | Account creation, sign-in/sign-out, a fitness questionnaire, and initial athlete-level assignment. |
| **Workout discovery** | Level-matched workouts with phases, exercise targets, instructions, and available exercise media. |
| **Interactive sessions** | Exercise navigation, set/rep/weight logging, timed efforts, adjustable timers, set deletion, and pause/resume behavior. |
| **Saved performance** | Completed workouts and exercise-level results saved to Supabase, with expandable and deletable history entries. |
| **Optional weight recommendations** | Suggested weight adjustments informed by recent history for the same exercise; the athlete decides whether to apply them. |
| **Training-level progression** | Recent-history analysis, progression-status reporting, and user-initiated advancement when eligible. |

## How the training workflow connects

**Assess → Discover → Train → Review → Progress**

The initial assessment establishes a starting level for workout discovery. During a workout, the athlete manually records completed repetitions and other exercise results. Saved exercise history supports later weight recommendations, while the profile reports training-level progression status.

### Recommendation is not automatic adjustment

Weight recommendations use recent recorded performance for the same exercise. The athlete chooses whether to apply the suggestion and can edit the weight manually. Rep targets come from the selected workout, and the athlete records the repetitions actually completed.

Level progression is a separate behavior: the profile evaluates recent history and lets an eligible athlete choose to advance. Neither workflow silently changes the training plan. Assessment, recommendation, and progression behavior use deterministic application logic rather than a generative-AI coach.

Exact decision rules, thresholds, and implementation details remain private.

## Engineering scope

**Interactive workout state.** I implemented the in-session experience across exercise navigation, logged sets, timer adjustment, and pause/resume behavior. This is the core workflow shown in the app rather than a collection of disconnected screens.

**Authentication and persistence.** I connected account access to the workout experience and implemented database persistence for completed sessions and exercise-level results. History supports review and deletion as well as later recommendation and progression checks.

**Cross-platform interface.** I built the responsive UI and design system with React Native, Expo, and NativeWind, using Expo Router for navigation. The project targets native mobile devices and includes a static web build; configured targets are not a claim of public deployment or testing on every device.

## Technology

| Area | Implementation |
| --- | --- |
| Languages | Primarily JavaScript/JSX, with some TypeScript project files |
| Application | React 19, React Native 0.81, Expo 54 |
| Navigation | Expo Router |
| UI and styling | NativeWind / Tailwind CSS, Expo Image, Expo Haptics, React Native Reanimated, React Native Animatable |
| Data fetching and state | TanStack React Query |
| Backend and authentication | Supabase |
| Database | Supabase-hosted PostgreSQL |
| Session persistence | AsyncStorage on native devices; browser local storage on web |
| Build configuration | Expo EAS internal-preview and production mobile build profiles; static web build |

## Development status

Athlete Moves is a functional development prototype tested by its developer, not a publicly released production app. Mobile build profiles are configured, but that does not imply an App Store or Google Play release. No public web deployment is claimed.

Validation currently includes developer testing and linting. An automated test suite and production monitoring/error reporting have not yet been implemented. Security verification and further production-readiness work remain outstanding.

## Source availability

This is a documentation-only showcase, not a runnable application distribution. The working repository remains private. Application source, database schemas, backend configuration, private athlete information, and unpublished business rules are excluded.

## About the developer

**Greyson Denison-Fischer** — Computer Science student at Central Michigan University, graduating May 2027 and seeking new-graduate software engineering opportunities.

[LinkedIn](https://www.linkedin.com/in/greyson-fischer/) · [GitHub](https://github.com/dgreyson3)
